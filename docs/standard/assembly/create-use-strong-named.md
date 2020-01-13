---
title: Crear y utilizar ensamblados con nombre seguro
ms.date: 08/19/2019
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, about strong-named assemblies
- strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, scenarios
- assemblies [.NET Framework], strong-named
- strong-named assemblies, loading into trusted application domains
- assembly binding, strong-named
ms.assetid: ffbf6d9e-4a88-4a8a-9645-4ce0ee1ee5f9
ms.openlocfilehash: 18a0b7d657290835a34c705513d0d7a4ccbfc61c
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75738687"
---
# <a name="create-and-use-strong-named-assemblies"></a>Crear y utilizar ensamblados con nombre seguro

Un nombre seguro se compone de la identidad del ensamblado, es decir, de su nombre de texto simple, número de versión e información sobre referencia cultural (si se proporciona), más una clave pública y una firma digital. Se genera a partir de un archivo de ensamblado mediante la clave privada correspondiente. (El archivo de ensamblado contiene el manifiesto del ensamblado, que a su vez contiene los nombres y códigos hash de todos los archivos que forman el ensamblado).

> [!WARNING]
> Para garantizar la seguridad, no confíe únicamente en el uso de nombres seguros. Estos solo proporcionan una identidad única.

Un ensamblado con nombre seguro solo puede usar tipos de otros ensamblados con nombre seguro. De lo contrario, se pondría en peligro la integridad del ensamblado con nombre seguro.

> [!NOTE]
> Aunque .NET Core admite ensamblados con nombre seguro, y todos los ensamblados de la biblioteca .NET Core están firmados, la mayoría de los ensamblados de terceros no necesitan nombres seguros. Para obtener más información, consulte [Strong Name Signing (Firma con nombre seguro)](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) en GitHub.

## <a name="strong-name-scenario"></a>Escenario de nombre seguro

En el siguiente escenario se firma un ensamblado con un nombre seguro y después se hace referencia a él con ese nombre.

1. El ensamblado A se crea con un nombre seguro mediante uno de los métodos siguientes:

    - Usar un entorno de desarrollo que admita la creación de nombres seguros, como Visual Studio.

    - Crear un par de claves criptográficas mediante la [herramienta de nombre seguro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) y asignar ese par de claves al ensamblado con un compilador de línea de comandos o [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md). Windows SDK proporciona ambas utilidades Sn.exe y Al.exe.

2. El entorno de desarrollo o la herramienta firma el hash del archivo que contiene el manifiesto del ensamblado con la clave privada del programador. Esta firma digital se almacena en el archivo portable ejecutable (PE) que contiene el manifiesto del ensamblado A.

3. El ensamblado B es un consumidor del ensamblado A. La sección de referencia del manifiesto del ensamblado B contiene un token que representa la clave pública del ensamblado A. Un token es una parte de la clave pública completa y se usa en lugar de la propia clave para ahorrar espacio.

4. Common Language Runtime comprueba la firma de nombre seguro cuando el ensamblado se ubica en la caché global de ensamblados. Al enlazar por nombre seguro en tiempo de ejecución, Common Language Runtime compara la clave almacenada en el manifiesto del ensamblado B con la clave usada para generar el nombre seguro del ensamblado A. Si se superan las comprobaciones de seguridad de .NET Framework y el enlace se realiza correctamente, el ensamblado B tiene la garantía de que los bits del ensamblado A no se han alterado y que esos bits proceden realmente de los desarrolladores del ensamblado A.

> [!NOTE]
> Este escenario no soluciona los problemas de confianza. Los ensamblados pueden llevar firmas completas de Microsoft Authenticode además de un nombre seguro. Las firmas de Authenticode incluyen un certificado que establece la confianza. Es importante tener en cuenta que los nombres seguros no requieren que el código se firme de esta manera. Los nombres seguros solo proporcionan una identidad única.

## <a name="bypass-signature-verification-of-trusted-assemblies"></a>Omitir la verificación de la firma de ensamblados de confianza

A partir de .NET Framework 3.5 Service Pack 1, las firmas de nombre seguro no se validan cuando un ensamblado se carga en un dominio de aplicación de plena confianza, como el dominio de aplicación predeterminado para la zona `MyComputer`. Esta característica se denomina omisión de nombres seguros. En un entorno de plena confianza, las peticiones de <xref:System.Security.Permissions.StrongNameIdentityPermission> siempre se realizan correctamente para los ensamblados de plena confianza firmados, independientemente de su firma. La característica de omisión de nombres seguros evita en esta situación la sobrecarga innecesaria por comprobación de firmas de nombre seguro de ensamblados de plena confianza, lo que permite cargar los ensamblados con mayor rapidez.

La característica de omisión se aplica a cualquier ensamblado que esté firmado con un nombre seguro y que:

- tenga plena confianza sin evidencia <xref:System.Security.Policy.StrongName> (por ejemplo, con la evidencia de zona `MyComputer`);

- se cargue en un <xref:System.AppDomain> de plena confianza;

- se cargue desde una ubicación en la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> de ese <xref:System.AppDomain>;

- no tenga firma retrasada.

Esta característica puede deshabilitarse en aplicaciones concretas o en todo un equipo. Vea [Cómo: Deshabilitar la característica de omisión de nombres seguros](disable-strong-name-bypass-feature.md).

## <a name="related-topics"></a>Temas relacionados

|Title|Descripción|
|-----------|-----------------|
|[Cómo: Crear un par de claves privada y pública](create-public-private-key-pair.md)|Describe cómo crear un par de claves criptográficas para firmar un ensamblado.|
|[Cómo: Firmar un ensamblado con un nombre seguro](sign-strong-name.md)|Describe cómo crear un ensamblado con nombre seguro.|
|[Nombres seguros mejorados](enhanced-strong-naming.md)|Describe las mejoras en nombres seguros en .NET Framework 4.5.|
|[Cómo: Hacer referencia a un ensamblado con nombre seguro](reference-strong-named.md)|Describe cómo hacer referencia a tipos o recursos en un ensamblado con nombre seguro en tiempo de compilación o tiempo de ejecución.|
|[Cómo: Deshabilitar la característica de omisión de nombres seguros](disable-strong-name-bypass-feature.md)|Describe cómo deshabilitar la característica que omite la validación de firmas de nombre seguro. Esta característica puede deshabilitarse para todas las aplicaciones o para aplicaciones específicas.|
|[Creación de ensamblados](create.md)|Proporciona información general sobre los ensamblados de archivos individuales y múltiples archivos.|
|[Cómo retrasar la firma de un ensamblado en Visual Studio](/visualstudio/ide/managing-assembly-and-manifest-signing#how-to-sign-an-assembly-in-visual-studio)|Explica cómo firmar un ensamblado con un nombre seguro después de haber creado el ensamblado.|
|[Sn.exe (herramienta de nombre seguro)](../../framework/tools/sn-exe-strong-name-tool.md)|Describe la herramienta incluida en .NET Framework que ayuda a crear ensamblados con nombres seguros. Esta herramienta proporciona opciones para la administración de claves, así como para la generación y comprobación de firmas.|
|[Al.exe (Assembly Linker)](../../framework/tools/al-exe-assembly-linker.md)|Describe la herramienta incluida en .NET Framework que genera un archivo que tiene un manifiesto de ensamblado a partir de archivos de recursos o módulos.|
