---
title: -filealign (Opciones del compilador de C#)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: 2655e0216a412053e052ab2ec2fcc8c68ea4f968
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88268054"
---
# <a name="-publicsign-c-compiler-options"></a><span data-ttu-id="a1b5f-102">-filealign (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="a1b5f-102">-publicsign (C# Compiler Options)</span></span>

<span data-ttu-id="a1b5f-103">Esta opción hace que el compilador aplique una clave pública pero no firma el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a1b5f-103">This option causes the compiler to apply a public key but does not actually sign the assembly.</span></span> <span data-ttu-id="a1b5f-104">La opción **-publicsign** también establece un bit en el ensamblado que indica el entorno de tiempo de ejecución en el que el archivo está firmado.</span><span class="sxs-lookup"><span data-stu-id="a1b5f-104">The **-publicsign** option also sets a bit in the assembly that tells the runtime that the file is actually signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1b5f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1b5f-105">Syntax</span></span>

```console
-publicsign
```

## <a name="arguments"></a><span data-ttu-id="a1b5f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a1b5f-106">Arguments</span></span>

<span data-ttu-id="a1b5f-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a1b5f-107">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1b5f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1b5f-108">Remarks</span></span>

<span data-ttu-id="a1b5f-109">La opción **-publicsign** requiere el uso de [-keyfile](keyfile-compiler-option.md) o [-keycontainer](keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a1b5f-109">The **-publicsign** option requires the use of the [-keyfile](keyfile-compiler-option.md) or [-keycontainer](keycontainer-compiler-option.md).</span></span> <span data-ttu-id="a1b5f-110">Las opciones **keyfile** o **keycontainer** especifican la clave pública.</span><span class="sxs-lookup"><span data-stu-id="a1b5f-110">The **keyfile** or **keycontainer** options specify the public key.</span></span>

<span data-ttu-id="a1b5f-111">Las opciones **-publicsign** y **-delaysign** son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="a1b5f-111">The **-publicsign** and **-delaysign** options are mutually exclusive.</span></span>

<span data-ttu-id="a1b5f-112">A veces llamada "firma falsa" o "firma OSS", la firma pública incluye la clave pública en un ensamblado de salida y establece la marca "firmado", pero en realidad no firma el ensamblado con una clave privada.</span><span class="sxs-lookup"><span data-stu-id="a1b5f-112">Sometimes called "fake sign" or "OSS sign", public signing includes the public key in an output assembly and sets the "signed" flag, but doesn't actually sign the assembly with a private key.</span></span> <span data-ttu-id="a1b5f-113">Esto es útil para proyectos de código abierto donde la gente quiere crear ensamblados que sean compatibles con los ensamblados "totalmente firmados" publicados, pero que no tengan acceso a la clave privada utilizada para firmar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="a1b5f-113">This is useful for open source projects where people want to build assemblies which are compatible with the released "fully signed" assemblies, but don't have access to the private key used to sign the assemblies.</span></span> <span data-ttu-id="a1b5f-114">Dado que casi ningún consumidor necesita realmente comprobar si el ensamblado está completamente firmado, estos ensamblados públicamente creados se pueden utilizar en casi todos los escenarios en los que se utilizaría el ensamblado totalmente firmado.</span><span class="sxs-lookup"><span data-stu-id="a1b5f-114">Since almost no consumers actually need to check if the assembly is fully signed, these publicly built assemblies are useable in almost every scenario where the fully signed one would be used.</span></span>

### <a name="to-set-this-compiler-option-in-a-csproj-file"></a><span data-ttu-id="a1b5f-115">Cómo establecer esta opción del compilador en un archivo .csproj</span><span class="sxs-lookup"><span data-stu-id="a1b5f-115">To set this compiler option in a csproj file</span></span>

<span data-ttu-id="a1b5f-116">Abra el archivo .csproj de un proyecto y agregue el elemento siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1b5f-116">Open the .csproj file for a project, and add the following element:</span></span>

```xml
<PublicSign>true</PublicSign>
```

## <a name="see-also"></a><span data-ttu-id="a1b5f-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1b5f-117">See also</span></span>

- [<span data-ttu-id="a1b5f-118">Opción -delaysign del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="a1b5f-118">C# Compiler -delaysign option</span></span>](delaysign-compiler-option.md)
- [<span data-ttu-id="a1b5f-119">Opción -keyfile del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="a1b5f-119">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="a1b5f-120">Opción -keycontainer del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="a1b5f-120">C# Compiler -keycontainer option</span></span>](keycontainer-compiler-option.md)
- [<span data-ttu-id="a1b5f-121">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="a1b5f-121">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="a1b5f-122">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="a1b5f-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
