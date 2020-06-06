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
ms.openlocfilehash: c632a15552c8ba5743aac1309098b7d7ef949bbd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088006"
---
# <a name="cryptography-settings-schema"></a>Esquema de la configuración de criptografía
El esquema de la configuración de criptografía contiene elementos que especifican cómo asignar nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)

|Elemento|Descripción|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](cryptoclasses-element.md)|Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el **\<nameEntry>** elemento.|  
|[**\<cryptoClass**>](cryptoclass-element.md)|Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el **\<nameEntry>** elemento.|  
|[**\<cryptographySettings**>](cryptographysettings-element.md)|Contiene la configuración de criptografía.|  
|[**\<cryptoNameMapping**>](cryptonamemapping-element.md)|Contiene asignaciones de clases a nombres descriptivos.|  
|[**\<mscorlib>** elemento para la configuración de criptografía](mscorlib-element-for-cryptography-settings.md)|Contiene el **\<cryptographySettings>** elemento.|  
|[**\<nameEntry>**](nameentry-element.md)|Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.|  
|[**\<oidEntry>**](oidentry-element.md)|Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.|  
|[**\<oidMap>**](oidmap-element.md)|Contiene asignaciones de OID ASN.1 a clases.|  
  
## <a name="see-also"></a>Vea también

- [Esquema de los archivos de configuración](../index.md)
- [Servicios criptográficos](../../../../standard/security/cryptographic-services.md)
