---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 12b45c08a3d8dc69e740ce77d0d2abd097907ac2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="contract"></a>Contrato
Contrato  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase Contrato no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase Contrato tiene las siguientes propiedades:  
  
### <a name="appdomainid"></a>AppDomainId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El id. del appdomain de appdomain que hospeda el contrato.  
  
### <a name="behaviors"></a>Comportamientos  
 Tipo de datos: matriz de comportamientos  
  
 Tipo de acceso: solo lectura  
  
 Los comportamientos asociados a este contrato.  
  
### <a name="name"></a>nombre  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre del contrato en WSDL.  
  
### <a name="namespace"></a>Espacio de nombres  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El espacio de nombres del elemento `portType` en WSDL.  
  
### <a name="operations"></a>Operaciones  
 Tipo de datos: matriz de operación  
  
 Tipo de acceso: solo lectura  
  
 Las operaciones de este contrato.  
  
### <a name="processid"></a>ProcessId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El Identificador del proceso del proceso que hospeda el contrato.  
  
### <a name="ref"></a>ref  
 Tipo de datos: Contrato  
  
 Tipo de acceso: solo lectura  
  
 El tipo de devolución de llamada cuando el contrato es un contrato dúplex.  
  
### <a name="sessionmode"></a>SessionMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Indica si el contrato requiere el enlace asociado a este contrato para utilizar las sesiones del canal.  
  
### <a name="type"></a>Tipo  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Tipo del contrato.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Description.ContractDescription>
