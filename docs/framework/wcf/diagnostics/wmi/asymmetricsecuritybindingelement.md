---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: e968f5f2d7ffdb193b30762d32a47be3778b98dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621362"
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
  
 Tipo de acceso: De sólo lectura  
  
 El orden de cifrado de mensajes y firma para este enlace.  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Si el enlace requiere la confirmación de la firma.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
