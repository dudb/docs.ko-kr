---
title: "일반적으로 사용되는 컬렉션 형식 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- collections [.NET Framework], generic
- objects [.NET Framework], grouping in collections
- generics [.NET Framework], collections
- IList interface, grouping data in collections
- IDictionary interface, grouping data in collections
- grouping data in collections, generic collection types
- Collections classes
- generic collections
ms.assetid: f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55
caps.latest.revision: 29
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1f8d938d61492b4da4b35a56fba169a12ed4787e
ms.lasthandoff: 04/18/2017

---
# <a name="commonly-used-collection-types"></a>일반적으로 사용되는 컬렉션 형식
컬렉션 형식은 해시 테이블, 큐, 스택, 모음, 사전 및 목록과 같은 데이터 컬렉션의 일반적인 변형입니다.  
  
 컬렉션은 <xref:System.Collections.ICollection> 인터페이스, <xref:System.Collections.IList> 인터페이스, <xref:System.Collections.IDictionary> 인터페이스 또는 제네릭의 해당하는 부분에 기반합니다. <xref:System.Collections.IList> 인터페이스 및 <xref:System.Collections.IDictionary> 인터페이스는 모두 <xref:System.Collections.ICollection> 인터페이스에서 파생됩니다. 따라서 모든 컬렉션은 직접 또는 간접적으로 <xref:System.Collections.ICollection> 인터페이스에 기반합니다. <xref:System.Collections.IList> 인터페이스(예: <xref:System.Array>, <xref:System.Collections.ArrayList> 또는 <xref:System.Collections.Generic.List%601>)에 기반한 컬렉션이나 <xref:System.Collections.ICollection> 인터페이스(예: <xref:System.Collections.Queue>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Stack>, <xref:System.Collections.Concurrent.ConcurrentStack%601> 또는 <xref:System.Collections.Generic.LinkedList%601>)에서 모든 요소는 값만 포함합니다. <xref:System.Collections.IDictionary> 인터페이스(예: <xref:System.Collections.Hashtable> 및 <xref:System.Collections.SortedList> 클래스, <xref:System.Collections.Generic.Dictionary%602> 및 <xref:System.Collections.Generic.SortedList%602> 제네릭 클래스) 또는 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 클래스에 기반한 컬렉션에서 모든 요소는 키와 값을 모두 포함합니다.  <xref:System.Collections.ObjectModel.KeyedCollection%602> 클래스는 값과 해당 값에 포함된 키의 목록이며 이에 따라 목록과 사전처럼 동작하기 때문에 고유합니다.  
  
 강력한 형식을 지정하려면 제네릭 컬렉션을 사용하는 것이 가장 좋습니다. 그러나 언어가 제네릭을 지원하지 않는 경우 <xref:System.Collections> 네임스페이스는 <xref:System.Collections.CollectionBase>, <xref:System.Collections.ReadOnlyCollectionBase> 및 <xref:System.Collections.DictionaryBase>와 같은 기본 컬렉션을 포함합니다. 이 항목은 강력한 형식의 컬렉션 클래스를 만들기 위해 확장될 수 있는 추상 기본 클래스입니다. 다중 스레드 컬렉션에 효율적으로 액세스하려면 <xref:System.Collections.Concurrent> 네임스페이스에서 제네릭 컬렉션을 사용해야 합니다.  
  
 컬렉션은 요소 저장/정렬 방식과 검색/비교 수행 방식에 따라 달라질 수 있습니다. <xref:System.Collections.Queue> 클래스 및 <xref:System.Collections.Generic.Queue%601> 제네릭 클래스는 선입 선출 목록을 제공하는 반면 <xref:System.Collections.Stack> 클래스 및 <xref:System.Collections.Generic.Stack%601> 제네릭 클래스는 후입 선출 목록을 제공합니다. <xref:System.Collections.SortedList> 클래스 및 <xref:System.Collections.Generic.SortedList%602> 제네릭 클래스는 정렬된 버전의 <xref:System.Collections.Hashtable> 클래스 및 <xref:System.Collections.Generic.Dictionary%602> 제네릭 클래스를 제공합니다. <xref:System.Collections.Hashtable> 또는 <xref:System.Collections.Generic.Dictionary%602>의 요소는 요소의 키로만 액세스할 수 있지만 <xref:System.Collections.SortedList> 또는 <xref:System.Collections.ObjectModel.KeyedCollection%602>는 키 또는 요소의 인덱스로만 액세스할 수 있습니다. 컬렉션의 인덱스는 모두 영부터 시작됩니다(0부터 시작하지 않는 배열을 허용하는 <xref:System.Array> 제외).  
  
 LINQ to Objects 기능을 사용하면 개체 형식이 <xref:System.Collections.IEnumerable> 또는 <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 경우 LINQ 쿼리를 사용하여 메모리 내 개체에 액세스할 수 있습니다. LINQ 쿼리는 데이터 액세스를 위한 일반 패턴을 제공하고, 표준 `foreach` 루프에 비해 간결하고 쉽게 읽을 수 있으며, 필터링, 순서 지정 및 그룹화 기능을 제공합니다. 또한 LINQ 쿼리를 통해 성능을 향상시킬 수도 있습니다. 자세한 내용은 [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9) 및 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)를 참조하세요.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[컬렉션 및 데이터 구조](../../../docs/standard/collections/index.md)|스택, 큐, 목록, 배열 및 사전을 비롯하여 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서 사용 가능한 다양한 컬렉션 형식에 대해 설명합니다.|  
|[Hashtable 및 Dictionary 컬렉션 형식](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|제네릭 및 제네릭이 아닌 해시 기반 사전 형식의 기능을 설명합니다.|  
|[Sorted 컬렉션 형식](../../../docs/standard/collections/sorted-collection-types.md)|목록 및 집합용 정렬 기능을 제공하는 클래스에 대해 설명합니다.|  
|[제네릭](../../../docs/standard/generics/index.md)|[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서 제공하는 제네릭 컬렉션, 대리자 및 인터페이스를 비롯한 제네릭 기능에 대해 설명합니다. C#, Visual Basic 및 Visual C++의 기능 설명서 링크와 지원 기술(예: 리플렉션) 링크를 제공합니다.|  
  
## <a name="reference"></a>참조  
 <xref:System.Collections?displayProperty=fullName>  
  
 <xref:System.Collections.Generic?displayProperty=fullName>  
  
 <xref:System.Collections.ICollection?displayProperty=fullName>  
  
 <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>  
  
 <xref:System.Collections.IList?displayProperty=fullName>  
  
 <xref:System.Collections.Generic.IList%601?displayProperty=fullName>  
  
 <xref:System.Collections.IDictionary?displayProperty=fullName>  
  
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>
