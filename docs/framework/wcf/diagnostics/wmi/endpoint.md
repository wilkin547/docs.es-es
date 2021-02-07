---
description: 'Más información acerca de: punto de conexión'
title: Punto de conexión
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 1c28be37d1b1abfe1813e6da8903809affd309e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757467"
---
# <a name="endpoint"></a>Punto de conexión

Punto de conexión  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a>Métodos  

 La clase Endpoint define el método siguiente.  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetOperationCounterInstanceName](getoperationcounterinstancename.md)|Recupera el nombre de instancia del contador de rendimiento de la operación|  
  
## <a name="properties"></a>Propiedades  

 La clase Endpoint posee las siguientes propiedades:  
  
### <a name="address"></a>Dirección  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un URI que contiene la dirección del extremo.  
  
### <a name="addressheaders"></a>AddressHeaders  

 Tipo de datos: matriz de cadenas  
  
 Tipo de acceso: solo lectura  
  
 La colección de encabezados de dirección adjunta a este punto de conexión.  
  
### <a name="addressidentity"></a>AddressIdentity  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La identidad del punto de conexión.  
  
### <a name="appdomainid"></a>AppDomainId  

 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El id. del appdomain que hospeda al punto de conexión.  
  
### <a name="behaviors"></a>Comportamientos  

 Tipo de datos: matriz de comportamientos  
  
 Tipo de acceso: solo lectura  
  
 Colección de comportamientos implementada por este punto de conexión.  
  
### <a name="binding"></a>Enlace  

 Tipo de datos: enlace  
  
 Tipo de acceso: solo lectura  
  
 El enlace utilizado por este punto de conexión.  
  
### <a name="contractname"></a>ContractName  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Cadena que especifica qué contrato está exponiendo este punto de conexión.  
  
### <a name="counterinstancename"></a>CounterInstanceName  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre de la instancia del contador de rendimiento del extremo.  
  
### <a name="listenuri"></a>ListenUri  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El URI en el que el extremo realiza escuchas.  
  
### <a name="name"></a>Nombre  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre único de este punto de conexión.  
  
### <a name="processid"></a>ProcessId  

 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El Id. del proceso que hospeda al extremo.  
  
### <a name="ref"></a>ref  

 Tipo de datos: Contrato  
  
 Tipo de acceso: solo lectura  
  
 El contrato que este punto de conexión está exponiendo.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|
