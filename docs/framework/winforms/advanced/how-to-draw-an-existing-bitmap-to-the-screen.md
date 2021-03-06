---
title: '방법: 화면에 기존 비트맵 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: 2c66c1e2cdd0ee3f1a189b9a27284566210ef480
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>방법: 화면에 기존 비트맵 그리기
쉽게 화면에 기존 이미지를 그릴 수 있습니다. 만들려면 먼저는 <xref:System.Drawing.Bitmap> 파일 이름을 사용 하는 비트맵 생성자를 사용 하 여 개체 <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>합니다. 이 생성자는 BMP, GIF, JPEG, PNG 및 TIFF를 비롯 한 여러 가지 다른 파일 형식을 사용 하 여 이미지를 허용 합니다. 만든 후는 <xref:System.Drawing.Bitmap> 개체를 전달 하는 <xref:System.Drawing.Bitmap> 개체는 <xref:System.Drawing.Graphics.DrawImage%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 만듭니다는 <xref:System.Drawing.Bitmap> 개체 JPEG 파일에서 다음에 왼쪽 위 모퉁이 비트맵을 그립니다 (60, 10).  
  
 다음 그림에서는 지정 된 위치의 그린 비트맵을 보여 줍니다.  
  
 ![이미지 위치](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
