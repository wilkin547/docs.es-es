---
title: Reducción de dependencias de paquete con project.json
description: Reduzca las dependencias de paquete al crear bibliotecas basadas en project.json.
author: cartermp
ms.date: 06/20/2016
ms.openlocfilehash: 48ba3ef578388fd98fe7cb830df313512d359483
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740825"
---
# <a name="reducing-package-dependencies-with-projectjson"></a>Reducción de dependencias de paquete con project.json

En este artículo se analiza todo lo que necesita saber sobre cómo reducir las dependencias de paquete cuando se crean bibliotecas `project.json`. Al final de este artículo, habrá aprendido a redactar la biblioteca de manera tal que solo use las dependencias necesarias.

## <a name="why-its-important"></a>Por qué es importante

.NET Core es un producto que consta de paquetes NuGet.  Un paquete esencial es el [metapaquete .NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library), que es un paquete NuGet que consta de otros paquetes. Proporciona el conjunto de paquetes que se garantiza que funcionan con varias implementaciones de .NET, como .NET Framework, .NET Core y Xamarin/Mono.

Sin embargo, hay muchas posibilidades de que la biblioteca no use cada uno de los paquetes que contiene.  Cuando se crea una biblioteca y se la distribuye en NuGet, un procedimiento recomendado es "recortar" las dependencias para que solo queden los paquetes que realmente usa.  Esto da como resultado una superficie total menor de los paquetes NuGet.

## <a name="how-to-do-it"></a>Cómo hacerlo

Actualmente, no hay ningún comando de `dotnet` oficial que recorte las referencias de paquete.  En lugar de eso, deberá hacerlo de manera manual.  El proceso general tiene el aspecto siguiente:

1. Haga referencia a `NETStandard.Library` versión `1.6.0` en una sección `dependencies` del `project.json`.
2. Restaure paquetes con `dotnet restore` ([vea la nota](#dotnet-restore-note)) desde la línea de comandos.
3. Revise el archivo `project.lock.json` y encuentre la sección `NETStandard.Library`.  Se encuentra cerca del comienzo del archivo.
4. Copie todos los paquetes que aparecen en `dependencies`.
5. Quite la referencia a `.NETStandard.Library` y reemplácela por los paquetes copiados.
6. Quite las referencias a paquetes que no necesita.

Una de las siguientes formas le permite saber cuáles son los paquetes que no necesita:

1. Prueba y error. Esto implica quitar un paquete, realizar la restauración, ver si la biblioteca se compila y repetir este proceso.
2. Mediante el uso de una herramienta como [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) o [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector) para echar un vistazo a las referencias y ver las que realmente usa el código. De ese modo, puede quitar los paquetes que no corresponden a los tipos que usa.

## <a name="example"></a>Ejemplo

Imagine que escribió una biblioteca que brindó una funcionalidad adicional a los tipos de colección genéricos. Dicha biblioteca debería depender de paquetes como `System.Collections`, pero probablemente no dependería para nada de paquetes tales como `System.Net.Http`. Por lo tanto, sería bueno recortar las dependencias de paquete para que solo queden las que necesita esta biblioteca.

Para recortar esta biblioteca, comience con el archivo `project.json` y agregue una referencia a `NETStandard.Library` versión `1.6.0`.

```json
{
    "version":"1.0.0",
    "dependencies":{
        "NETStandard.Library":"1.6.0"
    },
    "frameworks": {
        "netstandard1.0": {}
     }
}
```

Luego, restaure los paquetes con `dotnet restore` ([vea la nota](#dotnet-restore-note)), revise el archivo `project.lock.json` y encuentre todos los paquetes restaurados para `NETStandard.Library`.

Aquí puede ver el aspecto que tiene la sección correspondiente del archivo `project.lock.json` cuando se tiene como destino `netstandard1.0`:

```json
"NETStandard.Library/1.6.0":{
    "type": "package",
    "dependencies": {
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    }
}
```

A continuación, copie las referencias de paquete a la sección `dependencies` del archivo `project.json` de la biblioteca, reemplazando la referencia de `NETStandard.Library`:

```json
{
    "version":"1.0.0",
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
    }
}
```

Es una enorme cantidad de paquetes, muchos de los cuales en realidad no son necesarios para extender los tipos de colección.  Puede quitar manualmente los paquetes o usar una herramienta como [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) o [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector/) para identificar los paquetes que el código realmente usa.

Aquí puede ver el aspecto que tendría un paquete recortado:

```json
{
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Linq": "4.1.0",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Runtime.Handles": "4.0.1",
        "System.Runtime.InteropServices": "4.1.0",
        "System.Runtime.InteropServices.RuntimeInformation": "4.0.0",
        "System.Threading.Tasks": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
     }
}
```

Ahora tiene una menor superficie que si hubiese dependido del metapaquete `NETStandard.Library`.

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
