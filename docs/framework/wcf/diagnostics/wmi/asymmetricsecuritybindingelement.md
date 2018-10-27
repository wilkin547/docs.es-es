---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 076313548828f1fbce9c68b48c0fa7db9cca095f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185123"
---
# <a name="asymmetricsecuritybindingelement"></a>AsymmetricSecurityBindingElement
AsymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
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
