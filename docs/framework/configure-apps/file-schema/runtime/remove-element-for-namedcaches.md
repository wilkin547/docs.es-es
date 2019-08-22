---
title: Elemento <remove> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: e9b126cee83bc8109606d915ea48549beea970c9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663472"
---
# <a name="remove-element-for-namedcaches"></a>\<Quite > elemento de \<namedCaches >
Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
\<remove>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Type  
 `None`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 `None`  
  
### <a name="child-elements"></a>Elementos secundarios  
 `None`  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.|  
  
## <a name="remarks"></a>Comentarios  
 El `remove` elemento quita una `namedCache` entrada de la colección de caché con nombre de una memoria caché.  
  
## <a name="see-also"></a>Vea también

- [\<namedCaches (elemento > (configuración de caché)](namedcaches-element-cache-settings.md)
