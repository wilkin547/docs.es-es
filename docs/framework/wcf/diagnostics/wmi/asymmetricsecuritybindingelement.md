---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 00485ff80a0064e700d99203de3aa581d3761f30
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255733"
---
# <a name="asymmetricsecuritybindingelement"></a>AsymmetricSecurityBindingElement

AsymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Syntax  
  
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

 Tipo de datos: cadena  
  
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

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
