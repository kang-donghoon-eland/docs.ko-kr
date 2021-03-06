---
title: F# 가이드
description: 이 가이드에서는 F#, .NET에서 실행되는 함수형 프로그래밍 언어에 대한 다양한 교육 자료에 대한 개요를 제공합니다.
author: jackfoxy
ms.date: 03/19/2018
ms.openlocfilehash: 393214a5da7445d8ee3dced844da8592f4ca6d31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="f-guide"></a>F# 가이드

F#은 .NET에서 실행되는 함수형 프로그래밍 언어입니다. 또한 객체에 대한 완벽한 지원을 제공하므로, 실용적인 솔루션을 위해 함수형 및 객체지향 프로그래밍을 혼합하여 모든 문제를 해결할 수 있습니다.

```fsharp
open System // Get access to functionality in System namespace.

// Function: takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

// Use the EntryPoint attribute to run the program.
[<EntryPoint>]
let main args =
    // Define a list of names
    let names = [| "Don"; "Julia"; "Xi" |]
    
    // Print a fun greeting for each name!
    names
    |> Array.map getGreeting
    |> Array.iter (fun greeting -> printfn "%s" greeting)

    0
```

F#의 핵심은 생산성입니다. 툴링 지원은 어디에서나 볼 수 있고 고급 기능으로 가득합니다.

## <a name="learning-f"></a>F # 학습 #

[F# 둘러보기](tour.md)는 많은 코드 샘플과 함께 언어의 주요 기능에 대한 개요를 제공합니다. F#을 처음 배우는 사람이거나 언어가 어떻게 작동하는지 알아보고 싶은 경우에 해당 문서를 권장합니다.

[Visual Studio에서 F #으로 시작](get-started/get-started-visual-studio.md) Windows 환경에서 Visual Studio IDE(Integraded Development Environment) 사용을 원한다면 해당 문서를 참고하십시오.

[Mac용 Visual Studio에서 F#으로 시작](get-started/get-started-with-visual-studio-for-mac.md) macOS 환경에서 Visual Studio IDE 사용을 원한다면 해당 문서를 참고하십시오.

[Visual Studio Code에서 F #으로 시작 하려면](get-started/get-started-vscode.md) 경우 플랫폼 간 경량 및 IDE 기능이 포함 된 발생 합니다.

[F#으로 .NET Core CLI 시작](get-started/get-started-command-line.md) 커맨드 라인 도구 사용을 원한다면 해당 문서를 참고하십시오.

[F# 및 Xamarin 시작](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) F#을 이용한 모바일 프로그래밍에 대한 문서입니다.

## <a name="references"></a>참조

[F # 언어 참조](language-reference/index.md) 은 F # 언어의 모든 기능에 대 한 공식 하 고 포괄적인 참조 합니다. 각 문서는 구문에 설명 하 고 코드 샘플을 보여 줍니다. 특정 문서를 찾습니다는 목차에서 필터 표시줄을 사용할 수 있습니다.

[F # 핵심 라이브러리 참조가](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) F # 핵심 라이브러리에 대 한 API 참조 됩니다.


## <a name="additional-guides"></a>추가 가이드

[F # 재미와 수익에 대 한](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) 는 종합적이 고 매우 자세한 र ् थ 학습 F #은 합니다. 내용과 작성자는 F # 커뮤니티에서 사랑 합니다. 대상 사용자는 주로 개발자에 게 개체 지향 프로그래밍 배경.

[F # 프로그래밍 Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) 학습 F #에 대 한 wikibook 됩니다. F # 커뮤니티의 제품 이기도합니다. 대상 그룹은 F #을 사용 하면 약간의 개체 지향 프로그래밍 배경을 처음 접하는 사용자입니다.

## <a name="learn-f-through-videos"></a>F # 비디오를 통한 학습

[YouTube에서 F # 자습서](https://www.youtube.com/watch?v=c7eNDJN758U) F # Visual Studio를 사용 하 여, 1.5 시간의 과정 동안 다양 한 좋은 예를 보여 주는에 충분히 소개 합니다. 대상 그룹에는 F #를 처음 접하는 Visual Studio 개발자입니다.

[F #을 사용한 프로그래밍 소개](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) 훌륭한 비디오 일련의 기본 편집기로 Visual Studio 코드를 사용 하 여입니다. 비디오 시리즈를 시작한 RPG 비디오 텍스트 기반 게임을 빌드하는 것과 끝납니다. 대상 사용자는 개발자 처음인 F # 및 Visual Studio Code (또는 간단한 IDE) 선호입니다.

[F #에 대 한 개발자를 위한 Visual Studio 2017의 새로운](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) 은 Visual Studio 2017에서 F #에 대 한 새로운 기능 중 일부를 보여 주는 비디오 과정입니다. 대상 그룹에는 F #를 처음 접하는 Visual Studio 개발자입니다.

## <a name="other-useful-resources"></a>기타 유용한 리소스

[F # 코드 조각 웹 사이트](http://www.fssnip.net) massive 완전 초보자를 위한에서 고급 코드 조각에 이르기까지 F #에서 모든 작업 하는 방법을 보여 주는 코드 조각 집합이 포함 되어 있습니다.

[F # 소프트웨어 Foundation Slack](http://fsharp.org/guides/slack/) 좋은 곳은 초보자를 위한 및 전문가 게 모두 매우 활성화가 있으며 프로그래머 세계에서 가장 F # 채팅에 사용할 수 있는의 일부입니다. 조인 하는 것이 좋습니다.

## <a name="the-f-software-foundation"></a>F# Software Foundation

Microsoft 기본 개발자의 F # 언어와 Visual Studio에서 해당 도구 이지만, F #는 또한 뒷받침 되며는 독립적인 foundation는 F # 소프트웨어 Foundation (FSSF).

F# Software Foundation의 임무는 F# 프로그래밍 언어를 홍보하고 보호하고 발전시키며, F# 프로그래머의 다양한 국제 커뮤니티의 성장을 지원하고 용이하게 만드는 것입니다.

자세한 내용을 알아보고 참여하려면 [fsharp.org](http://fsharp.org)를 참조하세요. 조인, 무료 및 foundation의 F # 개발자의 네트워크를 포기 하 고치지 않을!
