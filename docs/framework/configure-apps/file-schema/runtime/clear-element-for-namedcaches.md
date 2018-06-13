---
title: '&lt;Borrar&gt; (elemento) para &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: cdd6e4a4849a031dc6bcad909509498406fcb129
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745518"
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a>&lt;Borrar&gt; (elemento) para &lt;namedCaches&gt;
Todos los borra `namedCache` entradas en el `namedCaches` colección de una memoria caché.  
  
 \<System.Runtime.Caching >  
\<memoryCache >  
\<namedCaches >  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 `None`  
  
### <a name="child-elements"></a>Elementos secundarios  
 `None`  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Contiene una colección de valores de configuración para la instancia con nombre <xref:System.Runtime.Caching.MemoryCache> instancias.|  
  
## <a name="remarks"></a>Comentarios  
 El `clear` elemento borra todos los `namedCache` las entradas de la colección de caché con nombre de una memoria caché. Puede usar el `clear` elemento antes de usar el `add` elemento que se va a agregar una nueva entrada de caché con nombre para estar seguro de que no hay ninguna otra nombrar cachés en la colección.  
  
## <a name="see-also"></a>Vea también  
 [\<namedCaches > Element (Cache Settings)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
