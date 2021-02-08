---
description: 'Más información sobre: clase de operación'
title: Operation class
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 035c02bc05b7a64c5d15538001dbdcf2ec0b135b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803079"
---
# <a name="operation-class"></a>Operation class

Operación  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a>Métodos  

 La clase Operación no define ningún método.  
  
## <a name="properties"></a>Propiedades  

 La clase Operación tiene las siguientes propiedades:  
  
### <a name="action"></a>Acción  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La acción WS-Addressing del mensaje de solicitud.  
  
### <a name="asyncpattern"></a>AsyncPattern  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica que una operación se implementa de forma asincrónica mediante un `Begin` par de métodos [abrir/cerrar corchetes angulares] y `End` [abrir/cerrar corchetes angulares] en un contrato de servicio.  
  
### <a name="behaviors"></a>Comportamientos  

 Tipo de datos: matriz de comportamientos  
  
 Tipo de acceso: solo lectura  
  
 Los comportamientos asociados a esta operación.  
  
### <a name="iscallback"></a>IsCallback  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Verdadero cuando la operación es una operación de devolución de llamada.  
  
### <a name="isinitiating"></a>IsInitiating  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si el método implementa una operación que puede iniciar una sesión en el servidor.  
  
### <a name="isoneway"></a>IsOneWay  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si una operación devuelve un mensaje de respuesta.  
  
### <a name="isterminating"></a>IsTerminating  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si una operación devuelve un mensaje de respuesta.  
  
### <a name="methodsignature"></a>MethodSignature  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La firma del método de la operación.  
  
### <a name="name"></a>Nombre  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre de la operación.  
  
### <a name="parametertypes"></a>ParameterTypes  

 Tipo de datos: matriz de cadenas  
  
 Tipo de acceso: solo lectura  
  
 Tipos de los parámetros de la operación.  
  
### <a name="replyaction"></a>ReplyAction  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El valor de la acción SOAP para el mensaje de respuesta de la operación.  
  
### <a name="returntype"></a>ReturnType  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Tipo devuelto de la operación.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.OperationDescription>
