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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 71d2edac1dd9a84c9d3c92049d2494c7c5bd54b0
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028227"
---
# <a name="cryptography-settings-schema"></a>Esquema de la configuración de criptografía
El esquema de la configuración de criptografía contiene elementos que especifican cómo asignar nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.  
  
 [**\<configuration>**](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [**\<mscorlib>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)  
  
 [**\<cryptographySettings>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)  
  
 [**\<cryptoNameMapping>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)  
  
 [**\<cryptoClasses>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)  
  
 [**\<cryptoClass>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)  
  
 [**\<nameEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)  
  
 [**\<oidMap>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)  
  
 [**\<oidEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)|Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento **\<nameEntry>**.|  
|[**\<cryptoClass**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el elemento **\<nameEntry>**.|  
|[**\<cryptographySettings**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)|Contiene la configuración de criptografía.|  
|[**\<cryptoNameMapping**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|Contiene asignaciones de clases a nombres descriptivos.|  
|[Elemento **\<mscorlib>** para la configuración de criptografía](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)|Contiene el elemento **\<cryptographySettings>**.|  
|[**\<nameEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)|Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.|  
|[**\<oidEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.|  
|[**\<oidMap>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|Contiene asignaciones de OID ASN.1 a clases.|  
  
## <a name="see-also"></a>Vea también  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Servicios criptográficos](../../../../../docs/standard/security/cryptographic-services.md)
