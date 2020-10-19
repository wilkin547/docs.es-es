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
# <a name="dotnet-nuget-verify"></a><span data-ttu-id="0d8f1-103">dotnet nuget verify</span><span class="sxs-lookup"><span data-stu-id="0d8f1-103">dotnet nuget verify</span></span>

<span data-ttu-id="0d8f1-104">**Este artículo se aplica a:** ✔️ SDK de .NET 5.0.100-rc.2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="0d8f1-104">**This article applies to:** ✔️ .NET 5.0.100-rc.2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0d8f1-105">Nombre</span><span class="sxs-lookup"><span data-stu-id="0d8f1-105">Name</span></span>

<span data-ttu-id="0d8f1-106">`dotnet nuget verify`: comprueba un paquete NuGet firmado.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-106">`dotnet nuget verify` - Verifies a signed NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0d8f1-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0d8f1-107">Synopsis</span></span>

```dotnetcli
dotnet nuget verify [<package-path(s)>]
    [--all]
    [--certificate-fingerprint <FINGERPRINT>]
    [-v|--verbosity <LEVEL>]

dotnet nuget verify -h|--help
```

## <a name="description"></a><span data-ttu-id="0d8f1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d8f1-108">Description</span></span>

<span data-ttu-id="0d8f1-109">El comando `dotnet nuget verify` comprueba un paquete NuGet firmado.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-109">The `dotnet nuget verify` command verifies a signed NuGet package.</span></span>

## <a name="arguments"></a><span data-ttu-id="0d8f1-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0d8f1-110">Arguments</span></span>

- **`package-path(s)`**

  <span data-ttu-id="0d8f1-111">Especifica la ruta de acceso al paquete que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-111">Specifies the file path to the package(s) to be verified.</span></span> <span data-ttu-id="0d8f1-112">Se pueden pasar varios argumentos de posición para comprobar varios paquetes.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-112">Multiple position arguments can be passed in to verify multiple packages.</span></span>

## <a name="options"></a><span data-ttu-id="0d8f1-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="0d8f1-113">Options</span></span>

- **`--all`**

  <span data-ttu-id="0d8f1-114">Especifica que en los paquetes se deben realizar todas las comprobaciones posibles.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-114">Specifies that all verifications possible should be performed on the package(s).</span></span> <span data-ttu-id="0d8f1-115">De forma predeterminada, solo se comprueban `signatures`.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-115">By default, only `signatures` are verified.</span></span>

> [!NOTE]
> <span data-ttu-id="0d8f1-116">En la actualidad, este comando solo admite la comprobación de `signature`.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-116">This command currently supports only `signature` verification.</span></span>

- **`--certificate-fingerprint <FINGERPRINT>`**

  <span data-ttu-id="0d8f1-117">Compruebe que el certificado del firmante coincide con una de las huellas digitales `SHA256` especificadas.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-117">Verify that the signer certificate matches with one of the specified `SHA256` fingerprints.</span></span> <span data-ttu-id="0d8f1-118">Esta opción se puede incluir varias veces para proporcionar varias huellas digitales.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-118">This option can be supplied multiple times to provide multiple fingerprints.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="0d8f1-119">Establece el nivel de detalle de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-119">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="0d8f1-120">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-120">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="0d8f1-121">De manera predeterminada, es `normal`.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-121">The default is `normal`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="0d8f1-122">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="0d8f1-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="0d8f1-123">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0d8f1-123">Examples</span></span>

- <span data-ttu-id="0d8f1-124">Comprobación de *foo.nupkg*:</span><span class="sxs-lookup"><span data-stu-id="0d8f1-124">Verify *foo.nupkg*:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg
  ```

- <span data-ttu-id="0d8f1-125">Comprobación de varios paquetes NuGet: *foo.nupkg* y *todos los archivos .nupkg en el directorio especificado*:</span><span class="sxs-lookup"><span data-stu-id="0d8f1-125">Verify multiple NuGet packages - *foo.nupkg* and *all .nupkg files in the directory specified*:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg c:\mydir\*.nupkg
  ```

- <span data-ttu-id="0d8f1-126">Comprobación de que la signatura de *foo.nupkg* coincide con la huella digital de certificado especificada:</span><span class="sxs-lookup"><span data-stu-id="0d8f1-126">Verify *foo.nupkg* signature matches with the specified certificate fingerprint:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039
  ```

- <span data-ttu-id="0d8f1-127">Comprobación de que la signatura de *foo.nupkg* coincide con una de las huellas digitales de certificado especificadas:</span><span class="sxs-lookup"><span data-stu-id="0d8f1-127">Verify *foo.nupkg* signature matches with one of the specified certificate fingerprints:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039 --certificate-fingerprint EC10992GG5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E027
  ```
