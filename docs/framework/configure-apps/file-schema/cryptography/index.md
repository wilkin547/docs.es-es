---
title: Esquema de la configuración de criptografía
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: a2aa56f8b2a92f906293adfae9d23ed8959336fb
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664293"
---
# <a name="cryptography-settings-schema"></a>Esquema de la configuración de criptografía
El esquema de la configuración de criptografía contiene elementos que especifican cómo asignar nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.  
  
 [ **\<configuration>** ](../configuration-element.md)  
  
 [ **\<mscorlib>** ](mscorlib-element-for-cryptography-settings.md)  
  
 [ **\<cryptographySettings>** ](cryptographysettings-element.md)  
  
 [ **\<cryptoNameMapping>** ](cryptonamemapping-element.md)  
  
 [ **\<cryptoClasses>** ](cryptoclasses-element.md)  
  
 [ **\<cryptoClass>** ](cryptoclass-element.md)  
  
 [ **\<nameEntry>** ](nameentry-element.md)  
  
 [ **\<oidMap>** ](oidmap-element.md)  
  
 [ **\<oidEntry>** ](oidentry-element.md)  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[ **\<cryptoClasses**>](cryptoclasses-element.md)|Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento **\<nameEntry>** .|  
|[ **\<cryptoClass**>](cryptoclass-element.md)|Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el elemento **\<nameEntry>** .|  
|[ **\<cryptographySettings**>](cryptographysettings-element.md)|Contiene la configuración de criptografía.|  
|[ **\<cryptoNameMapping**>](cryptonamemapping-element.md)|Contiene asignaciones de clases a nombres descriptivos.|  
|[Elemento **\<mscorlib>** para la configuración de criptografía](mscorlib-element-for-cryptography-settings.md)|Contiene el elemento **\<cryptographySettings>** .|  
|[ **\<nameEntry>** ](nameentry-element.md)|Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.|  
|[ **\<oidEntry>** ](oidentry-element.md)|Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.|  
|[ **\<oidMap>** ](oidmap-element.md)|Contiene asignaciones de OID ASN.1 a clases.|  
  
## <a name="see-also"></a>Vea también

- [Esquema de los archivos de configuración](../index.md)
- [Cryptographic Services](../../../../../docs/standard/security/cryptographic-services.md)
