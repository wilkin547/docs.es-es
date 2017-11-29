---
title: '&lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8e1cf4c4428814361a56b5fd06dcce9e1512c836
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltallowaccountsgt"></a>&lt;allowAccounts&gt;
Contiene una colección de elementos de configuración que especifica las cuentas de usuario para los procesos que hospedan servicios [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] y se concede el acceso de conexión al servicio de uso compartido.  
  
 \<system.serviceModel.activation >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|Agrega una cuenta de usuario para los procesos que hospedan los servicios [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] y tienen concedido acceso de conexión al servicio de uso compartido.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<NET.Pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) o [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)|Especifica la configuración para la Canalización de Red o servicios de uso compartido de TCP.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
