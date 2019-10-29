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
ms.openlocfilehash: 35ed53fc480e218df595794f80af2458f3ecec38
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039161"
---
# <a name="configuration-file-schema-for-the-net-framework"></a>Esquema de los archivos de configuración de .NET Framework

Los archivos de configuración son archivos XML estándar que se pueden utilizar para cambiar configuraciones y establecer directivas para las aplicaciones. El esquema de configuración de .NET Framework se compone de elementos que se pueden usar en los archivos de configuración para controlar el comportamiento de las aplicaciones. La tabla de contenido de esta sección refleja la jerarquía de esquema para el inicio, el tiempo de ejecución, la red y otros tipos de valores de configuración.

Para obtener información sobre los tipos, el formato y la ubicación de los archivos de configuración, vea [Configurar aplicaciones](../index.md). Familiarícese con XML para editar los archivos de configuración directamente.

> [!IMPORTANT]
> En los atributos y etiquetas XML de los archivos de configuración se distingue entre mayúsculas y minúsculas.

## <a name="in-this-section"></a>En esta sección

[ **\<elemento > de configuración** ](configuration-element.md)\
Elemento de nivel superior para todos los archivos de configuración.

[ **\<elemento > assemblyBinding** ](assemblybinding-element-for-configuration.md)\
Especifica la directiva de enlace del ensamblado en el nivel de configuración.

[ **\<elemento > linkedConfiguration** ](linkedconfiguration-element.md)\
Especifica un archivo de configuración para incluirlo.

\ del [esquema de configuración de inicio](./startup/index.md)
Elementos que especifican la versión de Common Language Runtime que se va a usar.

[Esquema de configuración de tiempo de ejecución](./runtime/index.md)\
Elementos que configuran el enlace de ensamblado y el comportamiento en tiempo de ejecución.

[Esquema de la configuración de red](./network/index.md)\
Elementos que especifican cómo se conecta el .NET Framework a Internet.

\ de [esquema de configuración de criptografía](./cryptography/index.md)
Elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.

\ de [esquema de secciones de configuración](configuration-sections-schema.md)
Elementos usados para crear y usar secciones de configuración para la configuración personalizada.

[Esquema de configuración de seguimiento y Depuración](./trace-debug/index.md)\
Elementos que especifican modificadores y agentes de escucha de seguimiento.

[Esquema de configuración de proveedor de lenguaje y Compilador](./compiler/index.md)\
Elementos que especifican la configuración del compilador para los proveedores de lenguaje disponibles.

\ del [esquema de configuración](application-settings-schema.md) de la aplicación
Elementos que permiten a una aplicación Windows Forms o ASP.NET almacenar y recuperar valores de ámbito de aplicación y de ámbito de usuario.

\ del [esquema de configuración](./appsettings/index.md) de la aplicación
Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.

\ del [esquema de configuración Web](./web/index.md)
Elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS. Se usa en los archivos *Aspnet.config*.

[Windows Forms esquema de configuración](winforms/index.md)\
Todos los elementos de la sección de configuración de la aplicación Windows Forms, que incluye personalizaciones como la compatibilidad con varios monitores y con un alto valor de PPP.

\ del [esquema de configuración de WCF](./wcf/index.md)
Todos los elementos que le permiten configurar el servicio WCF y las aplicaciones cliente.

[Sintaxis de directivas WCF](./wcf-directive/index.md)\
Describe la Directiva de `@ServiceHost`, que define los atributos específicos de la página utilizados por el compilador. SVC.

[Esquema de configuración de WIF](windows-identity-foundation/index.md)\
Todos los elementos del esquema de configuración de Windows Identity Foundation (WIF).

## <a name="related-sections"></a>Secciones relacionadas

\ del [esquema de configuración de comunicación remota](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))
Describe los elementos que configuran las aplicaciones cliente y servidor que implementa la comunicación remota.

\ del [esquema de configuración de ASP.net](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))
Describe los elementos que controlan el comportamiento de las aplicaciones web ASP.NET.

[Esquema de configuración de servicios Web](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))\
Describe los elementos que controlan el comportamiento de servicios Web de ASP.NET y sus clientes.

[Configurar aplicaciones de .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))\
Describe cómo configurar la seguridad, el enlace del ensamblado y la comunicación remota de .NET Framework.
