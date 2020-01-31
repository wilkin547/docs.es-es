---
title: Nombres seguros y bibliotecas de .NET
description: Procedimientos recomendados para nombres de seguros de las bibliotecas de .NET.
ms.date: 10/16/2018
ms.openlocfilehash: db268093b07a2ece7cdb8329fd789b52da9c5c32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744535"
---
# <a name="strong-naming"></a>Nombres seguros

Nombres seguros se refiere a firmar un ensamblado con una clave, generando un [ensamblado con nombre seguro](../assembly/strong-named.md). Una vez que un ensamblado tiene un nombre seguro, crea una identidad única en función del nombre y del número de versión del ensamblado y puede ayudar a evitar conflictos de ensamblado.

El inconveniente de los nombres seguros es que .NET Framework en Windows habilita la carga estricta de ensamblados una vez que un ensamblado tiene un nombre seguro. Una referencia de ensamblado con nombre seguro debe coincidir exactamente con la versión a la que un ensamblado hace referencia, obligando a los desarrolladores a [configurar redirecciones de enlace](../../framework/configure-apps/redirect-assembly-versions.md) cuando se usa el ensamblado:

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

Cuando los desarrolladores de .NET se quejan de los nombres seguros, normalmente se quejan de la carga estricta de los ensamblados. Afortunadamente, este problema está aislado en .NET Framework. .NET Core, Xamarin, UWP y la mayoría del resto de implementaciones de .NET no tienen carga estricta de ensamblados y quitan el principal inconveniente de los nombres seguros.

Un aspecto importante de los nombres seguros es que son virales: un ensamblado con nombre seguro solamente pueden hacer referencia otros ensamblados con nombre seguro. Si la biblioteca no tiene un nombre seguro, es que se ha excluido a los desarrolladores que están creando una aplicación o biblioteca que necesita nombres seguros para usarla.

Las ventajas de los nombres seguros son:

1. Otros ensamblados con nombre seguro pueden hacer referencia al ensamblado y usarlo.
2. El ensamblado se puede almacenar en la memoria caché global de ensamblados (GAC).
3. El ensamblado se puede cargar en paralelo con otras versiones de dicho ensamblado. Normalmente, las aplicaciones con arquitecturas de complemento requieren la carga de ensamblados en paralelo.

## <a name="create-strong-named-net-libraries"></a>Creación de bibliotecas de .NET con nombre seguro

Se deben asignar un nombre seguro a las bibliotecas de .NET de código abierto. La asignación de un nombre seguro a un ensamblado garantiza que la mayoría de los usuarios pueden usarlo y la carga estricta del ensamblado solo afecta a .NET Framework.

> [!NOTE]
> Esta guía es específica de las bibliotecas de .NET distribuidas públicamente, como las bibliotecas de .NET publicadas en NuGet.org. La mayoría de las aplicaciones .NET no necesitan nombres seguros y estos no se deben utilizar de forma predeterminada.

✔️ ES RECOMENDABLE usar nombres seguros en los ensamblados de la biblioteca.

✔️ ES RECOMENDABLE agregar la clave de nombres seguros al sistema de control de código fuente.

> Una clave disponible públicamente permite a los programadores modificar y volver a compilar el código fuente de la biblioteca con la misma clave.
>
> No debería publicar la clave de nombres seguros si se ha utilizado en el pasado para conceder permisos especiales en [escenarios de confianza parcial](../../framework/misc/using-libraries-from-partially-trusted-code.md). En caso contrario, podría poner en peligro los entornos existentes.

> [!IMPORTANT]
> Cuando se desea la identidad del publicador del código, se recomiendan [Authenticode](/windows-hardware/drivers/install/authenticode) y la [firma de paquetes NuGet](/nuget/create-packages/sign-a-package). La seguridad de acceso del código (CAS) no debe usarse como una mitigación de seguridad.

✔️ ES RECOMENDABLE incrementar la versión de ensamblado solamente en los cambios de versión principal para ayudar a los usuarios a reducir las redirecciones de enlace y la frecuencia con la que se actualizan.

> Obtenga más información sobre el [control de versiones y la versión del ensamblado](./versioning.md#assembly-version).

❌ NO agregue, quite ni cambie la clave de nombres seguros.

> La modificación de la clave de nombre seguro de un ensamblado cambia la identidad de este e interrumpe el código compilado que lo utiliza. Para más información, vea la información sobre [cambios importantes binarios](./breaking-changes.md#binary-breaking-change).

❌ NO publique versiones de la biblioteca tanto con nombre seguro como sin él. Por ejemplo, `Contoso.Api` y `Contoso.Api.StrongNamed`.

> La publicación de dos paquetes bifurca el ecosistema del desarrollador. Además, si una aplicación termina dependiendo de ambos paquetes, el desarrollador puede encontrar conflictos con el nombre de tipo. En lo que respecta a .NET, son tipos distintos en diferentes ensamblados.

>[!div class="step-by-step"]
>[Anterior](cross-platform-targeting.md)
>[Siguiente](nuget.md)
