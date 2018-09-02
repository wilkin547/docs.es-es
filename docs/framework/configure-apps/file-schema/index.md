---
title: Esquema de los archivos de configuración de .NET Framework
ms.date: 05/01/2017
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c7aebbfd0d25f6c5a9266857816a1723cb0c660e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466589"
---
# <a name="configuration-file-schema-for-the-net-framework"></a>Esquema de los archivos de configuración de .NET Framework

Los archivos de configuración son archivos XML estándar que se pueden utilizar para cambiar configuraciones y establecer directivas para las aplicaciones. El esquema de configuración de .NET Framework se compone de elementos que se pueden usar en los archivos de configuración para controlar el comportamiento de las aplicaciones. La tabla de contenido de esta sección refleja la jerarquía de esquema para el inicio, el tiempo de ejecución, la red y otros tipos de valores de configuración.

Para obtener información sobre los tipos, el formato y la ubicación de los archivos de configuración, vea el artículo [Configuring Apps](~/docs/framework/configure-apps/index.md) (Configurar aplicaciones). Familiarícese con XML para editar los archivos de configuración directamente.

> [!IMPORTANT]
> En los atributos y etiquetas XML de los archivos de configuración se distingue entre mayúsculas y minúsculas.

## <a name="in-this-section"></a>En esta sección

[**\<configuration>** Element](~/docs/framework/configure-apps/file-schema/configuration-element.md) (Elemento <configuration>): describe el elemento `<configuration>`, que es el elemento de nivel superior de todos los archivos de configuración.

[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) (Elemento <assemblyBinding>): especifica la directiva de enlace del ensamblado en el nivel de configuración.

[**\<linkedConfiguration>** Element](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) (Elemento <linkedConfiguration>): especifica un archivo de configuración para incluirlo.

[Startup Settings Schema](~/docs/framework/configure-apps/file-schema/startup/index.md) (Esquema de la configuración de inicio): describe los elementos que especifican la versión de Common Language Runtime que se va a usar.

[Runtime Settings Schema](~/docs/framework/configure-apps/file-schema/runtime/index.md) (Esquema de la configuración del tiempo de ejecución): describe los elementos que configuran el enlace del ensamblado y el comportamiento del tiempo de ejecución.

[Network Settings Schema](~/docs/framework/configure-apps/file-schema/network/index.md) (Esquema de la configuración de red): describe los elementos que especifican cómo se conecta .NET Framework a Internet.

[Cryptography Settings Schema](~/docs/framework/configure-apps/file-schema/cryptography/index.md) (Esquema de la configuración de criptografía): describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.

[Configuration Sections Schema](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) (Esquema de secciones de configuración): describe los elementos necesarios para crear y usar las secciones de configuración de valores personalizados.

[Trace and Debug Settings Schema](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) (Esquema de la configuración de seguimiento y depuración): describe los elementos que especifican los modificadores y agentes de escucha de seguimiento.

[Compiler and Language Provider Settings Schema](~/docs/framework/configure-apps/file-schema/compiler/index.md) (Esquema de configuración de compilador y proveedor de lenguaje): describe los elementos que especifican la configuración del compilador para los proveedores de lenguaje disponibles.

[Application Settings Schema](~/docs/framework/configure-apps/file-schema/application-settings-schema.md) (Esquema de la configuración de la aplicación): describe los elementos que permiten que una aplicación de formularios Windows Forms o ASP.NET almacene y recupere los valores del ámbito de usuario y del ámbito de aplicación.

[App Settings Schema](~/docs/framework/configure-apps/file-schema/appsettings/index.md) (Esquema de configuración de aplicaciones): contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.

[Web Settings Schema](~/docs/framework/configure-apps/file-schema/web/index.md) (Esquema de configuración web): describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS. Se usa en los archivos *Aspnet.config*.

[Windows Forms Configuration Schema](winforms/index.md) (Esquema de configuración de Windows Forms): todos los elementos de la sección de configuración de aplicaciones de Windows Forms, incluidas personalizaciones como la compatibilidad con varios monitores y valores altos de PPP.

[WCF Configuration Schema](~/docs/framework/configure-apps/file-schema/wcf/index.md) (Esquema de configuración de WCF): todos los elementos que permiten configurar el servicio WCF y las aplicaciones cliente.

[WCF Directive Syntax](~/docs/framework/configure-apps/file-schema/wcf-directive/index.md) (Sintaxis de directivas WCF): describe la directiva `@ServiceHost`, que define atributos específicos de página usados por el compilador .svc.

[WIF Configuration Schema](windows-identity-foundation/index.md) (Esquema de configuración de WIF): todos los elementos del esquema de configuración de Windows Identity Foundation (WIF).

## <a name="related-sections"></a>Secciones relacionadas

[Remoting Settings Schema](https://msdn.microsoft.com/library/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) (Esquema de configuración de la comunicación remota): describe los elementos que configuran las aplicaciones cliente y servidor que implementan la comunicación remota.

[ASP.NET Settings Schema](https://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx) (Esquema de configuración de ASP.NET): describe los elementos que controlan el comportamiento de las aplicaciones web ASP.NET.

[Web Services Settings Schema](https://msdn.microsoft.com/library/f84d6d55-1add-4eb7-ae46-33df5833ea2e) (Esquema de configuración de los servicios Web): describe los elementos que controlan el comportamiento de los servicios web ASP.NET y sus clientes.

[Configuring .NET Framework Apps](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42) (Configurar aplicaciones de .NET Framework): describe cómo configurar la seguridad, el enlace del ensamblado y la comunicación remota de .NET Framework.
