---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: f24865fb0affa7b4516a14fc05b905995826e82e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597676"
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
  
 Tipo de acceso: De sólo lectura  
  
 La Longitud máxima permitida de la matriz.  
  
### <a name="maxbytesperread"></a>MaxBytesPerRead  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El máximo permitido de bytes devueltos para cada lectura.  
  
### <a name="maxdepth"></a>MaxDepth  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 La profundidad de nodo anidada máxima por cada lectura.  
  
### <a name="maxnametablecharcount"></a>MaxNameTableCharCount  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 Los caracteres máximos permitidos en un nombre de tabla.  
  
### <a name="maxstringcontentlength"></a>MaxStringContentLength  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 Los caracteres máximos permitidos en contenido de elemento XML.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también
- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
