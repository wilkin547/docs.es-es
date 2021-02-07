---
description: 'Más información sobre: XmlDictionaryReaderQuotas'
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: d1450051e7107e9b92f848d26e6b182bfd2f2340
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756869"
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

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
