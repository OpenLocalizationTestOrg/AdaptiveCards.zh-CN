---
title: 呈现卡-iOS SDK
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: d47b94595c22afa51a0d4cf9666771203cd79c7e
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732919"
---
# <a name="render-a-card---ios"></a><span data-ttu-id="95299-102">呈现卡-iOS</span><span class="sxs-lookup"><span data-stu-id="95299-102">Render a card - iOS</span></span>

<span data-ttu-id="95299-103">下面介绍如何使用 iOS SDK 呈现卡。</span><span class="sxs-lookup"><span data-stu-id="95299-103">Here's how to render a card using the iOS SDK.</span></span>

## <a name="create-a-card-from-a-json-string"></a><span data-ttu-id="95299-104">从 JSON 字符串创建卡</span><span class="sxs-lookup"><span data-stu-id="95299-104">Create a card from a JSON string</span></span>

<span data-ttu-id="95299-105">AdaptiveCard 是从 JSON 字符串生成的</span><span class="sxs-lookup"><span data-stu-id="95299-105">AdaptiveCard is generated from JSON string</span></span>

```objective-c

NSString *jsonStr = @"{ \"type\": \"AdaptiveCard\", \"version\": \"1.0\", \"body\": [ { \"type\": \"Image\", \"url\": \"http://adaptivecards.io/content/adaptive-card-50.png\", \"horizontalAlignment\":\"center\" }, { \"type\": \"TextBlock\", \"horizontalAlignment\":\"center\", \"text\": \"Hello **Adaptive Cards!**\" } ], \"actions\": [ { \"type\": \"Action.OpenUrl\", \"title\": \"Learn more\", \"url\": \"http://adaptivecards.io\" }, { \"type\": \"Action.OpenUrl\", \"title\": \"GitHub\", \"url\": \"http://github.com/Microsoft/AdaptiveCards\" } ] }";
ACOAdaptiveCardParseResult *cardParseResult = [ACOAdaptiveCard fromJson:jsonStr];

/// access for parse warnings and errors
NSArray<NSError *> errors = cardParseResult.parseErrors;
NSArray<ACRParseWarning *> warnings = cardPraseResult.parseWarnings;
```

## <a name="render-a-card"></a><span data-ttu-id="95299-106">渲染卡片</span><span class="sxs-lookup"><span data-stu-id="95299-106">Render a Card</span></span>

<span data-ttu-id="95299-107">Rederer 采用自适应卡和主机配置。HostConfig 可以为 nil, 如果为 nil, 则使用默认值。</span><span class="sxs-lookup"><span data-stu-id="95299-107">Rederer takes adaptive card and host config. HostConfig can be nil, and if nil, default value will be used.</span></span>
<span data-ttu-id="95299-108">返回的 UIView 使用自动版式。</span><span class="sxs-lookup"><span data-stu-id="95299-108">Returned UIView uses autolayout.</span></span> <span data-ttu-id="95299-109">Width 将作为 widthConstraint 设置的值的约束。</span><span class="sxs-lookup"><span data-stu-id="95299-109">Width will be constraint to the value set by widthConstraint.</span></span> <span data-ttu-id="95299-110">如果使用0值, 则不会绑定它。</span><span class="sxs-lookup"><span data-stu-id="95299-110">If 0 value is used, it won't be bound.</span></span>
<span data-ttu-id="95299-111">高度未绑定, 返回时, 它将具有呈现的所有内容的总和的高度。</span><span class="sxs-lookup"><span data-stu-id="95299-111">Height is not bound, and when returned it will have the height of sums of all contents rendered.</span></span> <span data-ttu-id="95299-112">若要绑定视图维度, 请使用 NSLayoutConstraint。</span><span class="sxs-lookup"><span data-stu-id="95299-112">To bound the view dimension, please use NSLayoutConstraint.</span></span> <span data-ttu-id="95299-113">如果使用了 ACRViewController, 则可以从其 superview 的 viewcontroller 的 viewDidLayoutSubview 的上下文中访问该确切维度, 或使用具有相同名称的方法进行访问。</span><span class="sxs-lookup"><span data-stu-id="95299-113">The exact dimension is accessible from the context of viewDidLayoutSubview of its superview's viewcontroller or its method with the same name if ACRViewController is used.</span></span>

```objective-c
ACRRenderResult *renderResult;
if(cardParseResult.isValid){
    renderResult = [ACRRenderer render:cardParseResult.card config:nil widthConstraint:335];
}
``` 
### <a name="example"></a><span data-ttu-id="95299-114">示例</span><span class="sxs-lookup"><span data-stu-id="95299-114">Example</span></span>

```objective-c
--------------------------------------------------------------------------------
ViewController.m
--------------------------------------------------------------------------------
#import "ViewController.h"
#import <SafariServices/SafariServices.h>

@interface ViewController ()

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];

    NSString *jsonStr = @"{ \"type\": \"AdaptiveCard\", \"version\": \"1.0\", \"body\": [ { \"type\": \"Image\", \"url\": \"http://adaptivecards.io/content/adaptive-card-50.png\", \"horizontalAlignment\":\"center\" }, { \"type\": \"TextBlock\", \"horizontalAlignment\":\"center\", \"text\": \"Hello **Adaptive Cards!**\" } ], \"actions\": [ { \"type\": \"Action.OpenUrl\", \"title\": \"Learn more\", \"url\": \"http://adaptivecards.io\" }, { \"type\": \"Action.OpenUrl\", \"title\": \"GitHub\", \"url\": \"http://github.com/Microsoft/AdaptiveCards\" } ] }";
    ACRRenderResult *renderResult;
    ACOAdaptiveCardParseResult *cardParseResult = [ACOAdaptiveCard fromJson:jsonStr];
    if(cardParseResult.isValid){
        renderResult = [ACRRenderer render:cardParseResult.card config:nil widthConstraint:335];
    }

    if(renderResult.succeeded)
    {
        ACRView *ad = renderResult.view;
        ad.acrActionDelegate = self;
        
        UIView *view = self.view;
        view.autoresizingMask |= UIViewAutoresizingFlexibleHeight;
        [self.view addSubview:ad];
        ad.translatesAutoresizingMaskIntoConstraints = NO;
        
        [NSLayoutConstraint constraintWithItem:ad attribute:NSLayoutAttributeCenterX relatedBy:NSLayoutRelationEqual toItem:view attribute:NSLayoutAttributeCenterX multiplier:1.0 constant:0].active = YES;

        [NSLayoutConstraint constraintWithItem:ad attribute:NSLayoutAttributeCenterY relatedBy:NSLayoutRelationEqual toItem:view attribute:NSLayoutAttributeCenterY multiplier:1.0 constant:3].active = YES;
    }
}

- (void)didFetchUserResponses:(ACOAdaptiveCard *)card action:(ACOBaseActionElement *)action
{
    if(action.type == ACROpenUrl){
        NSURL *url = [NSURL URLWithString:[action url]];
        SFSafariViewController *svc = [[SFSafariViewController alloc] initWithURL:url];
        [self presentViewController:svc animated:YES completion:nil];
    }
}

@end

```

```swift
--------------------------------------------------------------------------------
ViewController.swft
--------------------------------------------------------------------------------

import UIKit
import SafariServices

class ViewController: UIViewController, ACRActionDelegate {

    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
        let jsonStr = "{ \"type\": \"AdaptiveCard\", \"version\": \"1.0\", \"body\": [ { \"type\": \"Image\", \"url\": \"http://adaptivecards.io/content/adaptive-card-50.png\", \"horizontalAlignment\":\"center\" }, { \"type\": \"TextBlock\", \"horizontalAlignment\":\"center\", \"text\": \"Hello **Adaptive Cards!**\" } ], \"actions\": [ { \"type\": \"Action.OpenUrl\", \"title\": \"Learn more\", \"url\": \"http://adaptivecards.io\" }, { \"type\": \"Action.OpenUrl\", \"title\": \"GitHub\", \"url\": \"http://github.com/Microsoft/AdaptiveCards\" } ] }";

        let cardParseResult = ACOAdaptiveCard.fromJson(jsonStr);
        if((cardParseResult?.isValid)!){
            let renderResult = ACRRenderer.render(cardParseResult!.card, config: nil, widthConstraint: 335);

            if(renderResult?.succeeded ?? false)
            {
                let ad = renderResult?.view;
                ad!.acrActionDelegate = (self as ACRActionDelegate);
                self.view.autoresizingMask = [.flexibleHeight];
                self.view.addSubview(ad!);
                ad!.translatesAutoresizingMaskIntoConstraints = false;
    
                NSLayoutConstraint(item: ad!, attribute: .centerX, relatedBy: .equal, toItem: view, attribute: .centerX, multiplier: 1.0, constant: 0).isActive = true;
                NSLayoutConstraint(item: ad!, attribute: .centerY, relatedBy: .equal, toItem: view, attribute: .centerY, multiplier: 1.0, constant: 3).isActive = true;
            }
        }
    }

    func didFetchUserResponses(_ card: ACOAdaptiveCard, action: ACOBaseActionElement)
    {
        if(action.type == ACRActionType.openUrl){
            let url = URL.init(string:action.url());
            let svc = SFSafariViewController.init(url: url!);
            self.present(svc, animated: true, completion: nil);
        }
    }

}
```