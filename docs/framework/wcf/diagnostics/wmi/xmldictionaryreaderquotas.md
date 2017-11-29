---
title: XmlDictionaryReaderQuotas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 980a7eacd095dc1b601d63f5a807f2e287c09885
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas
XmlDictionaryReaderQuotas  
  
## <a name="syntax"></a>Sintaxis  
  
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
  
## <a name="methods"></a>Métodos  
 La clase XmlDictionaryReaderQuotas no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase XmlDictionaryReaderQuotas tiene las propiedades siguientes:  
  
### <a name="maxarraylength"></a>MaxArrayLength  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 La Longitud máxima permitida de la matriz.  
  
### <a name="maxbytesperread"></a>MaxBytesPerRead  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El máximo permitido de bytes devueltos para cada lectura.  
  
### <a name="maxdepth"></a>MaxDepth  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 La profundidad de nodo anidada máxima por cada lectura.  
  
### <a name="maxnametablecharcount"></a>MaxNameTableCharCount  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 Los caracteres máximos permitidos en un nombre de tabla.  
  
### <a name="maxstringcontentlength"></a>MaxStringContentLength  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 Los caracteres máximos permitidos en contenido de elemento XML.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
