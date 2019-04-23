---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 0f86fc1b410753b5ec100f0a7d43de9badd1401b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59978073"
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
