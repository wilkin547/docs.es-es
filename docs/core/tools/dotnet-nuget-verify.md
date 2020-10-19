---
title: Comando dotnet nuget verify
description: El comando dotnet nuget verify comprueba un paquete firmado.
author: kartheekp-ms
ms.date: 10/08/2020
ms.openlocfilehash: 6cb368e2b6c203f3774b4450c0831c5d6b2dc0e8
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957118"
---
# <a name="dotnet-nuget-verify"></a>dotnet nuget verify

**Este artículo se aplica a:** ✔️ SDK de .NET 5.0.100-rc.2.x y versiones posteriores

## <a name="name"></a>Nombre

`dotnet nuget verify`: comprueba un paquete NuGet firmado.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet nuget verify [<package-path(s)>]
    [--all]
    [--certificate-fingerprint <FINGERPRINT>]
    [-v|--verbosity <LEVEL>]

dotnet nuget verify -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet nuget verify` comprueba un paquete NuGet firmado.

## <a name="arguments"></a>Argumentos

- **`package-path(s)`**

  Especifica la ruta de acceso al paquete que se va a comprobar. Se pueden pasar varios argumentos de posición para comprobar varios paquetes.

## <a name="options"></a>Opciones

- **`--all`**

  Especifica que en los paquetes se deben realizar todas las comprobaciones posibles. De forma predeterminada, solo se comprueban `signatures`.

> [!NOTE]
> En la actualidad, este comando solo admite la comprobación de `signature`.

- **`--certificate-fingerprint <FINGERPRINT>`**

  Compruebe que el certificado del firmante coincide con una de las huellas digitales `SHA256` especificadas. Esta opción se puede incluir varias veces para proporcionar varias huellas digitales.

* **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle de MSBuild. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. De manera predeterminada, es `normal`.

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

- Comprobación de *foo.nupkg*:

  ```dotnetcli
  dotnet nuget verify foo.nupkg
  ```

- Comprobación de varios paquetes NuGet: *foo.nupkg* y *todos los archivos .nupkg en el directorio especificado*:

  ```dotnetcli
  dotnet nuget verify foo.nupkg c:\mydir\*.nupkg
  ```

- Comprobación de que la signatura de *foo.nupkg* coincide con la huella digital de certificado especificada:

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039
  ```

- Comprobación de que la signatura de *foo.nupkg* coincide con una de las huellas digitales de certificado especificadas:

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039 --certificate-fingerprint EC10992GG5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E027
  ```
