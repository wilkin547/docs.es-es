---
title: AsymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 82e5365a440d103727f354e682d0ebecb5f46a46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="asymmetricsecuritybindingelement"></a>AsymmetricSecurityBindingElement
AsymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase AsymmetricSecurityBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase AsymmetricSecurityBindingElement tiene las propiedades siguientes:  
  
### <a name="messageprotectionorder"></a>MessageProtectionOrder  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El orden de cifrado de mensajes y firma para este enlace.  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Si el enlace requiere la confirmación de la firma.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
