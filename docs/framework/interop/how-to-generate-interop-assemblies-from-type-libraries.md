---
title: Procedimiento para generar ensamblados de interoperabilidad a partir de bibliotecas de tipos
description: Genere ensamblados de interoperabilidad a partir de bibliotecas de tipos. Use el importador de la biblioteca de tipos (Tlbimp.exe) para convertir coclases e interfaces de una biblioteca de tipos COM en metadatos.
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
ms.openlocfilehash: 6f54875d6aadb1da18cf25a1bec0a0e451f4a24c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619564"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="ecc13-104">Procedimiento para generar ensamblados de interoperabilidad a partir de bibliotecas de tipos</span><span class="sxs-lookup"><span data-stu-id="ecc13-104">How to: Generate Interop Assemblies from Type Libraries</span></span>
<span data-ttu-id="ecc13-105">El [importador de la biblioteca de tipos (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) es una herramienta de línea de comandos que convierte las coclases e interfaces contenidas en una biblioteca de tipos COM en metadatos.</span><span class="sxs-lookup"><span data-stu-id="ecc13-105">The [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="ecc13-106">Esta herramienta crea automáticamente un ensamblado de interoperabilidad y un espacio de nombres para la información de tipos.</span><span class="sxs-lookup"><span data-stu-id="ecc13-106">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="ecc13-107">Una vez que los metadatos de una clase están disponibles, los clientes administrados pueden crear instancias del tipo COM y llamar a sus métodos, como si se tratara de una instancia de .NET.</span><span class="sxs-lookup"><span data-stu-id="ecc13-107">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="ecc13-108">Tlbimp.exe convierte una biblioteca de tipos completa en metadatos de una vez y no se puede generar información de tipos para un subconjunto de los tipos definidos en una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="ecc13-108">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="ecc13-109">Para generar un ensamblado de interoperabilidad a partir de una biblioteca de tipos</span><span class="sxs-lookup"><span data-stu-id="ecc13-109">To generate an interop assembly from a type library</span></span>  
  
1. <span data-ttu-id="ecc13-110">Use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="ecc13-110">Use the following command:</span></span>  
  
     <span data-ttu-id="ecc13-111">**tlbimp** \<*type-library-file*></span><span class="sxs-lookup"><span data-stu-id="ecc13-111">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="ecc13-112">Agregar el modificador **/out:** genera un ensamblado de interoperabilidad con un nombre modificado, como LOANLib.dll.</span><span class="sxs-lookup"><span data-stu-id="ecc13-112">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="ecc13-113">Modificar el nombre de ensamblado de interoperabilidad puede ayudar a distinguirlo del archivo DLL original de COM e impedir problemas que pueden producirse al tener nombres duplicados.</span><span class="sxs-lookup"><span data-stu-id="ecc13-113">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecc13-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ecc13-114">Example</span></span>  
 <span data-ttu-id="ecc13-115">El comando siguiente genera el ensamblado Loanlib.dll en el espacio de nombres `Loanlib`.</span><span class="sxs-lookup"><span data-stu-id="ecc13-115">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```console  
tlbimp Loanlib.tlb  
```  
  
 <span data-ttu-id="ecc13-116">El comando siguiente genera un ensamblado de interoperabilidad con un nombre modificado (LOANLib.dll).</span><span class="sxs-lookup"><span data-stu-id="ecc13-116">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```console  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="ecc13-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecc13-117">See also</span></span>

- [<span data-ttu-id="ecc13-118">Importar una biblioteca de tipos como un ensamblado</span><span class="sxs-lookup"><span data-stu-id="ecc13-118">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="ecc13-119">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ecc13-119">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
