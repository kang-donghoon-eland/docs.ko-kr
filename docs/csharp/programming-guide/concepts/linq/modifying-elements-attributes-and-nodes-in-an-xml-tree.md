---
title: "XML 트리에서 요소, 특성 및 노드 수정3 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6fa51b22af73d716b01444540edb7c8d814cd293
ms.lasthandoff: 03/13/2017


---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a>XML 트리에서 요소, 특성 및 노드 수정
다음 표에는 요소, 해당 요소의 자식 요소 또는 특성을 수정하는 데 사용할 수 있는 메서드와 속성이 요약되어 있습니다.  
  
 다음 메서드는 <xref:System.Xml.Linq.XElement>를 수정합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>|요소를 구문 분석된 XML로 바꿉니다.|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName>|요소의 모든 내용(자식 노드와 특성)을 제거합니다.|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName>|요소의 특성을 제거합니다.|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName>|요소의 모든 내용(자식 노드와 특성)을 바꿉니다.|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName>|요소의 특성을 바꿉니다.|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName>|특성의 값을 설정합니다. 특성이 없으면 특성을 만듭니다. 값이 `null`로 설정되어 있으면 특성을 제거합니다.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName>|자식 요소의 값을 설정합니다. 요소가 없으면 요소를 만듭니다. 값이 `null`로 설정되어 있으면 요소를 제거합니다.|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>|요소의 내용(자식 노드)을 지정된 텍스트로 바꿉니다.|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName>|요소의 값을 설정합니다.|  
  
 다음 메서드는 <xref:System.Xml.Linq.XAttribute>를 수정합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>|특성의 값을 설정합니다.|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName>|특성의 값을 설정합니다.|  
  
 다음 메서드는 <xref:System.Xml.Linq.XNode>(<xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 포함)를 수정합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName>|노드를 새 내용으로 바꿉니다.|  
  
 다음 메서드는 <xref:System.Xml.Linq.XContainer>(<xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument>)를 수정합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName>|자식 노드를 새 내용으로 바꿉니다.|  
  
## <a name="see-also"></a>참고 항목  
 [XML 트리 수정(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)