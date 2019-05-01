---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 1d367d0c5d14e6e75539dd2b20cdffcf2b34963d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962791"
---
# <a name="securitybindingelement"></a>SecurityBindingElement
SecurityBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase SecurityBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase SecurityBindingElement posee las siguientes propiedades:  
  
### <a name="defaultalgorithmsuite"></a>DefaultAlgorithmSuite  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica los algoritmos que se van a utilizar con la clase.  
  
### <a name="includetimestamp"></a>IncludeTimestamp  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Valor booleano que especifica si cada mensaje contiene una marca de tiempo.  
  
### <a name="keyentropymode"></a>KeyEntropyMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Origen de la entropía utilizada para crear claves.  
  
### <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings  
 Tipo de datos: LocalServiceSecuritySettings  
  
 Tipo de acceso: De sólo lectura  
  
 Las propiedades de seguridad específicas del enlace del servicio local.  
  
### <a name="messagesecurityversion"></a>MessageSecurityVersion  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Versión utilizada para la seguridad del mensaje.  
  
### <a name="securityheaderlayout"></a>SecurityHeaderLayout  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Orden de los elementos en el encabezado de seguridad de este enlace.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
