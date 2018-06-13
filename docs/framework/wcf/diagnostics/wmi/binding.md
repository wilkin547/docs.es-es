---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: 0260b75a0f49e0f6f72d7d1eda642d0a494d2892
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487012"
---
# <a name="binding"></a>Enlaces
Enlace wmi  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase Binding no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase Binding tiene las propiedades siguientes.  
  
### <a name="bindingelements"></a>BindingElements  
 Tipo de datos: matriz de BindingElement  
  
 Tipo de acceso: solo lectura  
  
 La colección de elementos de enlace implementada por el enlace.  
  
### <a name="closetimeout"></a>CloseTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El intervalo de tiempo proporcionado para que se complete una operación de cierre.  
  
### <a name="name"></a>nombre  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre del enlace.  
  
### <a name="namespace"></a>Espacio de nombres  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Espacio de nombres XML del enlace.  
  
### <a name="opentimeout"></a>OpenTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El intervalo de tiempo proporcionado para que se complete una operación de apertura.  
  
### <a name="receivetimeout"></a>ReceiveTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El intervalo de tiempo proporcionado para que se complete una operación de recepción.  
  
### <a name="scheme"></a>Scheme  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El esquema de transporte de URI utilizado por los generadores de canales y de agentes de escucha creados por el enlace.  
  
### <a name="sendtimeout"></a>SendTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El intervalo de tiempo proporcionado para que se complete una operación de envío.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.Binding>
