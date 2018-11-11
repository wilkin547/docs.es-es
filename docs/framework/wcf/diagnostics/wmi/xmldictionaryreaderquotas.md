---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: 9bc519509b00383be333ac605688950d2709117c
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980536"
---
# <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas
XmlDictionaryReaderQuotas  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
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
