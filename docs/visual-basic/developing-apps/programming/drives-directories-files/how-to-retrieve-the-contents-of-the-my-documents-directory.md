---
title: "방법: Visual Basic에서 내 문서 디렉터리의 내용 검색"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3456984a697439a8c2ab7fb88f9f0f32d10cb0e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a>방법: Visual Basic에서 내 문서 디렉터리의 내용 검색
<xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> 개체를 사용하여 **내 문서**, **바탕 화면** 등의 많은 **모든 사용자** 디렉터리에서 읽을 수 있습니다.  
  
### <a name="to-read-from-the-my-documents-folder"></a>내 문서 폴더에서 읽으려면  
  
-   `ReadAllText` 메서드를 사용하여 특정 디렉터리에 있는 각 파일에서 텍스트를 읽습니다. 다음 코드에서는 디렉터리와 파일을 지정한 다음 `ReadAllText`를 사용하여 `patients`라는 문자열로 읽어옵니다.  
  
     [!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
