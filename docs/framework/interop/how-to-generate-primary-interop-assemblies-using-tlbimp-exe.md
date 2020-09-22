---
title: Procedimiento para generar ensamblados de interoperabilidad primarios mediante Tlbimp.exe
description: Obtenga información sobre cómo generar ensamblados de interoperabilidad primarios mediante el importador de la biblioteca de tipos (Tlbimp.exe) que proporciona Windows SDK.
ms.date: 03/30/2017
helpviewer_keywords:
- primary interop assemblies, generating
- Tlbimp.exe
- Type Library Importer
ms.assetid: 5419011c-6e57-40f6-8c65-386db8f7a651
ms.openlocfilehash: 56ce10e0b6f9be988a06d44550cd3b9dc2efd188
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554161"
---
# <a name="how-to-generate-primary-interop-assemblies-using-tlbimpexe"></a><span data-ttu-id="387c5-103">Procedimiento para generar ensamblados de interoperabilidad primarios mediante Tlbimp.exe</span><span class="sxs-lookup"><span data-stu-id="387c5-103">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>

<span data-ttu-id="387c5-104">Hay dos maneras de generar un ensamblado de interoperabilidad primario:</span><span class="sxs-lookup"><span data-stu-id="387c5-104">There are two ways to generate a primary interop assembly:</span></span>

- <span data-ttu-id="387c5-105">Mediante el [importador de la biblioteca de tipos (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) proporcionado por Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="387c5-105">Using the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) provided by the Windows SDK.</span></span>

  <span data-ttu-id="387c5-106">La manera más sencilla de generar ensamblados de interoperabilidad primarios es usar el [importador de la biblioteca de tipos (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="387c5-106">The most straightforward way to produce primary interop assemblies is to use the [Tlbimp.exe (Type Library Importer)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="387c5-107">Tlbimp.exe ofrece las siguientes medidas de protección:</span><span class="sxs-lookup"><span data-stu-id="387c5-107">Tlbimp.exe provides the following safeguards:</span></span>

  - <span data-ttu-id="387c5-108">Busca otros ensamblados de interoperabilidad primarios registrados antes de crear nuevos ensamblados de interoperabilidad para las referencias de biblioteca de tipos anidadas.</span><span class="sxs-lookup"><span data-stu-id="387c5-108">Checks for other registered primary interop assemblies before creating new interop assemblies for any nested type library references.</span></span>

  - <span data-ttu-id="387c5-109">No emite el ensamblado de interoperabilidad primario si no se especifica el contenedor o el nombre de archivo para asignar un nombre seguro al ensamblado de interoperabilidad primario.</span><span class="sxs-lookup"><span data-stu-id="387c5-109">Fails to emit the primary interop assembly if you do not specify either the container or file name to give the primary interop assembly a strong name.</span></span>

  - <span data-ttu-id="387c5-110">No emite un ensamblado de interoperabilidad primario si se omiten las referencias a los ensamblados dependientes.</span><span class="sxs-lookup"><span data-stu-id="387c5-110">Fails to emit a primary interop assembly if you omit references to dependent assemblies.</span></span>

  - <span data-ttu-id="387c5-111">No emite un ensamblado de interoperabilidad primario si se agregan referencias a ensamblados dependientes que no son ensamblados de interoperabilidad primarios.</span><span class="sxs-lookup"><span data-stu-id="387c5-111">Fails to emit a primary interop assembly if you add references to dependent assemblies that are not primary interop assemblies.</span></span>

- <span data-ttu-id="387c5-112">Creando ensamblados de interoperabilidad primarios manualmente en el código fuente usando un lenguaje compatible con Common Language Specification (CLS), como C#.</span><span class="sxs-lookup"><span data-stu-id="387c5-112">Creating primary interop assemblies manually in source code by using a language that is compliant with the Common Language Specification (CLS), such as C#.</span></span> <span data-ttu-id="387c5-113">Este enfoque es útil cuando no hay una biblioteca de tipos disponible.</span><span class="sxs-lookup"><span data-stu-id="387c5-113">This approach is useful when a type library is unavailable.</span></span>

<span data-ttu-id="387c5-114">Es necesario disponer de un par de claves criptográficas para firmar un ensamblado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="387c5-114">You must have a cryptographic key pair to sign the assembly with a strong name.</span></span> <span data-ttu-id="387c5-115">Para más información, vea [Crear un par de claves](../../standard/assembly/create-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="387c5-115">For details, see [Creating A Key Pair](../../standard/assembly/create-public-private-key-pair.md).</span></span>

### <a name="to-generate-a-primary-interop-assembly-using-tlbimpexe"></a><span data-ttu-id="387c5-116">Para generar ensamblados de interoperabilidad primarios mediante Tlbimp.exe</span><span class="sxs-lookup"><span data-stu-id="387c5-116">To generate a primary interop assembly using Tlbimp.exe</span></span>

1. <span data-ttu-id="387c5-117">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="387c5-117">At the command prompt, type:</span></span>

    <span data-ttu-id="387c5-118">**tlbimp** *tlbfile*  **/primary /keyfile:** *filename* **/out:** *assemblyname*</span><span class="sxs-lookup"><span data-stu-id="387c5-118">**tlbimp** *tlbfile*  **/primary /keyfile:** *filename* **/out:** *assemblyname*</span></span>

    <span data-ttu-id="387c5-119">En este comando, *archivo_tlb* es el archivo que contiene la biblioteca de tipos COM, *nombre_de_archivo* es el nombre del contenedor o archivo que contiene el par de claves y *nombre_de_ensamblado* es el nombre del ensamblado que se va a firmar con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="387c5-119">In this command, *tlbfile* is the file containing the COM type library, *filename* is the name of the container or file that contains the key pair, and *assemblyname* is the name of the assembly to sign with a strong name.</span></span>

<span data-ttu-id="387c5-120">Los ensamblados de interoperabilidad primarios solo pueden hacer referencia a otros ensamblados de interoperabilidad primarios.</span><span class="sxs-lookup"><span data-stu-id="387c5-120">Primary interop assemblies can reference only other primary interop assemblies.</span></span> <span data-ttu-id="387c5-121">Si el ensamblado hace referencia a tipos de una biblioteca de tipos COM de terceros, debe obtener un ensamblado de interoperabilidad primario desde el publicador antes de poder generar el ensamblado de interoperabilidad primario.</span><span class="sxs-lookup"><span data-stu-id="387c5-121">If your assembly references types from a third-party COM type library, you must obtain a primary interop assembly from the publisher before you can generate your primary interop assembly.</span></span> <span data-ttu-id="387c5-122">Si usted es el publicador, debe generar un ensamblado de interoperabilidad primario para la biblioteca de tipos dependiente antes de generar el ensamblado de interoperabilidad primario que hace la referencia.</span><span class="sxs-lookup"><span data-stu-id="387c5-122">If you are the publisher, you must generate a primary interop assembly for the dependent type library before generating the referencing primary interop assembly.</span></span>

<span data-ttu-id="387c5-123">Si un ensamblado de interoperabilidad primario dependiente tiene un número de versión distinto del de la biblioteca de tipos original, no se reconoce cuando se instala en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="387c5-123">A dependent primary interop assembly with a version number that differs from that of the original type library is not discoverable when installed in the current directory.</span></span> <span data-ttu-id="387c5-124">Debe registrar el ensamblado de interoperabilidad primario dependiente en el Registro de Windows o usar la opción **/reference** para asegurarse de que Tlbimp.exe encuentre el archivo DLL dependiente.</span><span class="sxs-lookup"><span data-stu-id="387c5-124">You must either register the dependent primary interop assembly in the Windows registry or use the **/reference** option to be sure that Tlbimp.exe finds the dependent DLL.</span></span>

<span data-ttu-id="387c5-125">También puede encapsular varias versiones de una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="387c5-125">You can also wrap multiple versions of a type library.</span></span> <span data-ttu-id="387c5-126">Para obtener instrucciones, vea [Cómo: Incluir varias versiones de bibliotecas de tipos](/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="387c5-126">For instructions, see [How to: Wrap Multiple Versions of Type Libraries](/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="387c5-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="387c5-127">Example</span></span>

<span data-ttu-id="387c5-128">En el siguiente ejemplo se importa la biblioteca de tipos COM `LibUtil.tlb` y se firma el ensamblado `LibUtil.dll` con un nombre seguro usando el archivo de clave `CompanyA.snk`.</span><span class="sxs-lookup"><span data-stu-id="387c5-128">The following example imports the COM type library `LibUtil.tlb` and signs the assembly `LibUtil.dll` with a strong name using the key file `CompanyA.snk`.</span></span> <span data-ttu-id="387c5-129">Si se omite un nombre de espacio de nombres específico, este ejemplo genera el espacio de nombres predeterminado `LibUtil`.</span><span class="sxs-lookup"><span data-stu-id="387c5-129">By omitting a specific namespace name, this example produces the default namespace, `LibUtil`.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /out:LibUtil.dll
```

<span data-ttu-id="387c5-130">Para lograr un nombre más descriptivo (siguiendo las directrices de nomenclatura *NombreProveedor*.*NombreBiblioteca*), en el ejemplo siguiente se invalida el nombre predeterminado del archivo de ensamblado y el nombre de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="387c5-130">For a more descriptive name (using the *VendorName*.*LibraryName* naming guideline), the following example overrides the default assembly file name and namespace name.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /namespace:CompanyA.LibUtil /out:CompanyA.LibUtil.dll
```

<span data-ttu-id="387c5-131">En el siguiente ejemplo se importa `MyLib.tlb`, que hace referencia al ensamblado `CompanyA.LibUtil.dll`, y se firma el ensamblado `CompanyB.MyLib.dll` con un nombre seguro usando el archivo de clave `CompanyB.snk`.</span><span class="sxs-lookup"><span data-stu-id="387c5-131">The following example imports `MyLib.tlb`, which references `CompanyA.LibUtil.dll`, and signs the assembly `CompanyB.MyLib.dll` with a strong name using the key file `CompanyB.snk`.</span></span> <span data-ttu-id="387c5-132">El espacio de nombres `CompanyB.MyLib` invalida el nombre de espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="387c5-132">The namespace, `CompanyB.MyLib`, overrides the default namespace name.</span></span>

```console
tlbimp MyLib.tlb /primary /keyfile:CompanyB.snk /namespace:CompanyB.MyLib /reference:CompanyA.LibUtil.dll /out:CompanyB.MyLib.dll
```

## <a name="see-also"></a><span data-ttu-id="387c5-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="387c5-133">See also</span></span>

- [<span data-ttu-id="387c5-134">Cómo: Registrar ensamblados de interoperabilidad primarios</span><span class="sxs-lookup"><span data-stu-id="387c5-134">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)
