---
title: Nombres seguros y las bibliotecas de .NET
description: Prácticas recomendadas para las bibliotecas de .NET nomenclatura seguras.
author: jamesnk
ms.author: mairaw
ms.date: 10/16/2018
ms.openlocfilehash: e3f7d443eb9acc84c800ea2611b803733085391c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372814"
---
# <a name="strong-naming"></a>Nombres seguros

Nombres seguros se refiere al firmar un ensamblado con una clave, generar un [ensamblados](../../framework/app-domains/strong-named-assemblies.md). Una vez un ensamblado con nombre seguro, crea una identidad única en función del número de versión de nombre y el ensamblado, y puede ayudar a evitar conflictos de ensamblado.

La desventaja de nombre seguro es que .NET Framework en Windows permite strict carga de ensamblados una vez que un ensamblado tiene un nombre seguro. Una referencia de ensamblado con nombre seguro debe coincidir exactamente con la versión que se hace referencia a un ensamblado, los desarrolladores a [configurar redirecciones de enlace](../../framework/configure-apps/redirect-assembly-versions.md) cuando se usa el ensamblado:

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly" publicKeyToken="32ab4ba45e0a69a1" culture="neutral" />
            <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

Cuando los desarrolladores de .NET se quejan nombres seguros, lo están normalmente queja es strict carga de ensamblados. Afortunadamente, este problema está aislado en .NET Framework. La mayoría de otras implementaciones. NET, Xamarin, UWP y .NET core no tiene la carga de ensamblados estricta y quita la principal desventaja de nombres seguros.

Un aspecto importante de nombre seguro es que resulta viral: una fuerte denominado ensamblado sólo pueden hacer referencia otros seguro ensamblados con nombre. Si la biblioteca no está segura con nombre, a continuación, ha excluido a los desarrolladores que crean una aplicación o biblioteca que necesita nombres seguros de utilizarla.

Las ventajas de nombres seguros son:

1. El ensamblado se puede hacer referencia a y usar otros ensamblados con nombre seguro.
2. El ensamblado se puede almacenar en caché de ensamblados Global (GAC).
3. El ensamblado se puede cargar en paralelo con otras versiones del ensamblado. Carga de ensamblados en paralelo se requieren habitualmente las aplicaciones con arquitecturas para complementos.

## <a name="create-strong-named-net-libraries"></a>Crear seguro con el nombre de las bibliotecas de .NET

Se deben asignar un nombre seguro las bibliotecas .NET de código abierto. Un ensamblado de nombres seguros garantiza la mayoría de los usuarios puede usarla y estricta ensamblado cargar solo afecta a .NET Framework.

> [!NOTE]
> Esta guía es específica a las bibliotecas de .NET distribuidas públicamente, como bibliotecas de .NET publican en NuGet.org. Nombres seguros no es necesaria para la mayoría de las aplicaciones de .NET y no se deben realizar de forma predeterminada.

**Considere la posibilidad de ✔️** seguro nombres a los ensamblados de la biblioteca.

**Considere la posibilidad de ✔️** comprobación de la clave utilizada para el nombre seguro en el sistema de control de código fuente.

> Una clave disponible públicamente permite a los programadores modificar y volver a compilar el código fuente de biblioteca con la misma clave.

> [!IMPORTANT]
> Cuando se desea una identidad de cifrado, [Authenticode](/windows-hardware/drivers/install/authenticode) y [firma del paquete NuGet](/nuget/create-packages/sign-a-package) se recomiendan. No se deben usar nombres seguros de consideraciones de seguridad.

**Considere la posibilidad de ✔️** incrementar la versión de ensamblado en los cambios de versión principal solo para ayudar a los usuarios a reducir las redirecciones de enlace, y con qué frecuencia se actualizan.

> Obtenga más información sobre [control de versiones y la versión del ensamblado](./versioning.md#assembly-version).

**NO ❌** agregar, quitar o cambiar la clave de nomenclatura segura.

> Modificar la clave de nomenclatura segura de un ensamblado cambia la identidad del ensamblado e interrumpe el código compilado que lo utiliza. Para obtener más información, consulte [binario cambios importantes](./breaking-changes.md#binary-breaking-change).

**❌ NO** publicar versiones con nombre seguro y sin seguro-nombre de la biblioteca. Por ejemplo, `Contoso.Api` y `Contoso.Api.StrongNamed`.

> Publicar dos bifurcaciones de paquetes en el ecosistema del desarrollador. Además, si una aplicación termina según ambos paquetes el desarrollador puede producirse conflictos de nombre de tipo. En lo que se refiere .NET son tipos diferentes en distintos ensamblados.

>[!div class="step-by-step"]
[Anterior](./cross-platform-targeting.md)
[Siguiente](./nuget.md)
