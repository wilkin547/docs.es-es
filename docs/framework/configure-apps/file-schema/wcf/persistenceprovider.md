---
title: '&lt;persistenceProvider&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b506b8ef14246ee954adb0a16102f4bb208106b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltpersistenceprovidergt"></a>&lt;persistenceProvider&gt;
Especifica el tipo de la implementación de proveedor de persistencia que se va a usar, así como el tiempo de espera que se va a utilizar en las operaciones de persistencia.  
  
 \<sistema. ServiceModel >  
\<comportamientos >  
\<serviceBehaviors >  
\<comportamiento >  
\<persistenceProvider >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"  
   type="String" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|persistenceOperationTimeout|Un valor <xref:System.TimeSpan> que especifica el tiempo de espera usado en las operaciones de persistencia. El valor predeterminado es "00: 00:30".|  
|type|Una cadena que especifica el tipo del generador del proveedor de persistencia que se va a usar.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<comportamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento especifica el proveedor de persistencia que se va a utilizar para serializar el estado de un servicio WCF. Se debería utilizar junto con `wsHttpContextBinding` que pasa la información de estado en encabezados HTTP.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>  
 <xref:System.ServiceModel.Persistence.PersistenceProvider>
