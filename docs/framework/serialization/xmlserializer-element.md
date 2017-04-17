---
title: "&lt;xmlSerializer&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<xmlSerializer> 요소"
  - "XML serialization, configuration"
  - "xmlSerializer 요소"
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;xmlSerializer&gt; 요소
<xref:System.Xml.Serialization.XmlSerializer>의 진행에 대한 추가 검사가 수행되었는지 여부를 지정합니다.  
  
## 구문  
  
```  
  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**checkDeserializeAdvances**|<xref:System.Xml.Serialization.XmlSerializer>의 진행률이 검사되었는지 여부를 지정합니다.  특성을 "true" 또는 "false"로 설정합니다.  기본값은 "true"입니다.|  
|**useLegacySerializationGeneration**|<xref:System.Xml.Serialization.XmlSerializer>가 C\# 코드를 파일에 쓴 다음 어셈블리로 컴파일하여 어셈블리를 생성하는 레거시 serialization 생성을 사용하는지 여부를 지정합니다.  기본값은 **false**입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<system.xml.serialization\> 요소](../../../docs/framework/serialization/system-xml-serialization-element.md)|<xref:System.Xml.Serialization.XmlSerializer> 및 <xref:System.Xml.Serialization.XmlSchemaImporter> 클래스에 대한 구성 설정을 포함합니다.|  
  
## 설명  
 기본적으로 <xref:System.Xml.Serialization.XmlSerializer>는 신뢰할 수 없는 데이터를 deserialize할 때 잠재적 서비스 거부 공격에 대한 추가 보안 계층을 제공합니다.  deserialization 도중 무한 루프의 탐지를 시도하여 이러한 보안을 제공합니다.  이러한 조건이 발견되면 "내부 오류: 내부 스트림으로 진행하지 못하여 deserialization하지 못했다"는 내용의 메시지와 함께 예외가 throw됩니다.  
  
 이 메시지가 반드시 서비스 거부 공격이 진행 중임을 의미하는 것은 아닙니다.  드문 경우지만 무한 루프 검색 메커니즘이 가양성\(false positive\)을 생성하여 적법한 들어오는 메시지에 대해 예외가 throw될 수도 있습니다.  특정 응용 프로그램에서 적법한 메시지가 이러한 추가 보호 계층에 의해 거부된 경우 **checkDeserializeAdvances** 특성을 "false"로 설정하십시오.  
  
## 예제  
 다음 코드 예제에서는 **checkDeserializeAdvances** 특성을 "false"로 설정합니다.  
  
```  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Xml.Serialization.XmlSerializer>   
 [\<system.xml.serialization\> 요소](../../../docs/framework/serialization/system-xml-serialization-element.md)   
 [XML 및 SOAP Serialization](../../../docs/framework/serialization/xml-and-soap-serialization.md)