---
title: "XmlDictionaryReaderQuotas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# XmlDictionaryReaderQuotas
XmlDictionaryReaderQuotas  
  
## Sintaxis  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## Métodos  
 La clase XmlDictionaryReaderQuotas no define ningún método.  
  
## Propiedades  
 La clase XmlDictionaryReaderQuotas tiene las propiedades siguientes:  
  
### MaxArrayLength  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 La Longitud máxima permitida de la matriz .  
  
### MaxBytesPerRead  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El máximo permitido de bytes devueltos para cada lectura.  
  
### MaxDepth  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 La profundidad de nodo anidada máxima por cada lectura.  
  
### MaxNameTableCharCount  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 Los caracteres máximos permitidos en un nombre de tabla.  
  
### MaxStringContentLength  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 Los caracteres máximos permitidos en contenido de elemento XML.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.Xml.XmlDictionaryReaderQuotas>   
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>