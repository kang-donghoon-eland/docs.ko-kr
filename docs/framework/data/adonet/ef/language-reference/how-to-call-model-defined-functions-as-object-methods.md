---
title: "방법: 모델 정의 함수를 개체 메서드로 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33bae8a8-4ed8-4a1f-85d1-c62ff288cc61
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 방법: 모델 정의 함수를 개체 메서드로 호출
이 항목에서는 모델 정의 함수를 <xref:System.Data.Objects.ObjectContext> 개체의 메서드 또는 사용자 지정 클래스의 정적 메서드로 호출하는 방법에 대해 설명합니다.  *모델 정의 함수*는 개념적 모델에 정의되는 함수입니다.  이 항목의 절차에서는 이러한 함수를 LINQ to Entities 쿼리에서 호출하는 대신 직접 호출하는 방법에 대해 설명합니다.  LINQ to Entities 쿼리에서 모델 정의 함수를 호출하는 방법은 [방법: 쿼리에서 모델 정의 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)을 참조하세요.  
  
 모델 정의 함수를 <xref:System.Data.Objects.ObjectContext> 메서드 또는 사용자 지정 클래스의 정적 메서드로 호출하려면 먼저 메서드를 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>가 있는 모델 정의 함수로 매핑해야 합니다.  그러나 <xref:System.Data.Objects.ObjectContext> 클래스의 메서드를 정의하는 경우에는 <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> 속성을 사용하여 LINQ 공급자를 노출해야 하고, 사용자 지정 클래스의 정적 메서드를 정의하는 경우에는 <xref:System.Linq.IQueryable.Provider%2A> 속성을 사용하여 LINQ 공급자를 노출해야 합니다.  자세한 내용은 다음 절차 아래에 나오는 예제를 참조하세요.  
  
 다음 절차에서는 모델 정의 함수를 <xref:System.Data.Objects.ObjectContext> 개체의 메서드 및 사용자 지정 클래스의 정적 메서드로 호출하는 방법에 대해 간단히 설명합니다.  절차 다음에 나오는 예제에서는 절차의 단계를 보다 자세히 설명합니다.  이러한 절차에서는 사용자가 개념적 모델에서 함수를 정의했다고 가정합니다.  자세한 내용은 [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/ko-kr/0dad7b8b-58f6-4271-b238-f34810d68e5f)을 참조하세요.  
  
### 모델 정의 함수를 ObjectContext 개체의 메서드로 호출하려면  
  
1.  Entity Framework 도구에 의해 자동으로 생성된 <xref:System.Data.Objects.ObjectContext> 클래스에서 파생되는 partial 클래스를 확장하기 위해 소스 파일을 추가합니다.  CLR 스텁을 별도의 소스 파일에서 정의하면 파일을 다시 생성할 때 변경 내용이 손실되지 않습니다.  
  
2.  다음 작업을 수행하는 <xref:System.Data.Objects.ObjectContext> 클래스에 CLR\(공용 언어 런타임\) 메서드를 추가합니다.  
  
    -   개념적 모델에 정의된 함수로 매핑합니다.  메서드를 매핑하려면 메서드에 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 적용해야 합니다.  특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> 매개 변수는 개념적 모델의 네임스페이스 이름이고, 특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> 매개 변수는 개념적 모델의 함수 이름입니다.  LINQ에서 함수 이름을 확인할 때는 대\/소문자가 구분됩니다.  
  
    -   <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> 속성에 의해 반환된 <xref:System.Linq.IQueryProvider.Execute%2A> 메서드의 결과를 반환합니다.  
  
3.  메서드를 <xref:System.Data.Objects.ObjectContext> 클래스 인스턴스의 멤버로 호출합니다.  
  
### 모델 정의 함수를 사용자 지정 클래스의 정적 메서드로 호출하려면  
  
1.  다음 작업을 수행하는 정적 메서드가 포함된 응용 프로그램에 클래스를 추가합니다.  
  
    -   개념적 모델에 정의된 함수로 매핑합니다.  메서드를 매핑하려면 메서드에 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 적용해야 합니다.  특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> 매개 변수는 개념적 모델의 네임스페이스 이름이고, 특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> 매개 변수는 개념적 모델의 함수 이름입니다.  
  
    -   <xref:System.Linq.IQueryable> 인수를 받아들입니다.  
  
    -   <xref:System.Linq.IQueryable.Provider%2A> 속성에 의해 반환된 <xref:System.Linq.IQueryProvider.Execute%2A> 메서드의 결과를 반환합니다.  
  
2.  메서드를 사용자 지정 클래스의 정적 메서드 멤버로 호출합니다.  
  
## 예제  
 **모델 정의 함수를 ObjectContext 개체의 메서드로 호출**  
  
 다음 예제에서는 모델 정의 함수를 <xref:System.Data.Objects.ObjectContext> 개체의 메서드로 호출하는 방법에 대해 설명합니다.  이 예제에서는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/ko-kr/f16cd988-673f-4376-b034-129ca93c7832)을 사용합니다.  
  
 지정된 제품의 제품 수익을 반환하는 다음 개념적 모델 함수를 살펴보세요.  개념적 모델에 함수를 추가하는 방법은 [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/ko-kr/0dad7b8b-58f6-4271-b238-f34810d68e5f)를 참조하세요.  
  
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/obj/x86/debug/edmxresourcestoembed/adventureworks.csdl#4)]
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/obj/x86/debug/edmxresourcestoembed/adventureworks.csdl#4)]
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#4)]  
  
## 예제  
 다음 코드에서는 위의 개념적 모델 함수로 매핑되는 `AdventureWorksEntities` 클래스에 메서드를 추가합니다.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#2)]
 [!code-vb[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#2)]  
  
## 예제  
 다음 코드에서는 위의 메서드를 호출하여 지정된 제품의 제품 수익을 표시합니다.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#3)]
 [!code-vb[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#3)]  
  
## 예제  
 다음 예제에서는 컬렉션을 반환하는 모델 정의 함수를 <xref:System.Linq.IQueryable%601> 개체로 호출하는 방법에 대해 설명합니다.  제공된 제품 ID의 모든 `SalesOrderDetails`를 반환하는 다음 개념적 모델 함수를 살펴보세요.  
  
 [!code-xml[DP L2E Methods on ObjectContext#7](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#7)]  
  
## 예제  
 다음 코드에서는 위의 개념적 모델 함수로 매핑되는 `AdventureWorksEntities` 클래스에 메서드를 추가합니다.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#8)]
 [!code-vb[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#8)]  
  
## 예제  
 다음 코드에서는 메서드를 호출합니다.  반환된 <xref:System.Linq.IQueryable%601> 쿼리는 각 `SalesOrderDetail`의 품목 합계를 반환하도록 보다 구체화됩니다.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#9)]
 [!code-vb[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#9)]  
  
## 예제  
 **모델 정의 함수를 사용자 지정 클래스의 정적 메서드로 호출**  
  
 다음 예제에서는 모델 정의 함수를 사용자 지정 클래스의 정적 메서드로 호출하는 방법에 대해 설명합니다.  이 예제에서는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/ko-kr/f16cd988-673f-4376-b034-129ca93c7832)을 사용합니다.  
  
> [!NOTE]
>  모델 정의 함수를 사용자 지정 클래스의 정적 메서드로 호출할 때 모델 정의 함수는 컬렉션을 받아들이고 컬렉션의 값 집계를 반환해야 합니다.  
  
 SalesOrderDetail 컬렉션의 제품 수익을 반환하는 다음 개념적 모델 함수를 살펴보세요.  개념적 모델에 함수를 추가하는 방법은 [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/ko-kr/0dad7b8b-58f6-4271-b238-f34810d68e5f)를 참조하세요.  
  
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/obj/x86/debug/edmxresourcestoembed/adventureworks.csdl#1)]
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/obj/x86/debug/edmxresourcestoembed/adventureworks.csdl#1)]
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#1)]  
  
## 예제  
 다음 코드에서는 위의 개념적 모델 함수로 매핑되는 정적 메서드가 포함된 응용 프로그램에 클래스를 추가합니다.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#5)]
 [!code-vb[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#5)]  
  
## 예제  
 다음 코드에서는 위의 메서드를 호출하여 SalesOrderDetail 컬렉션의 제품 수익을 표시합니다.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#6)]
 [!code-vb[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#6)]  
  
## 참고 항목  
 [.edmx File Overview](http://msdn.microsoft.com/ko-kr/f4c8e7ce-1db6-417e-9759-15f8b55155d4)   
 [LINQ to Entities의 쿼리](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)   
 [LINQ to Entities 쿼리의 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)