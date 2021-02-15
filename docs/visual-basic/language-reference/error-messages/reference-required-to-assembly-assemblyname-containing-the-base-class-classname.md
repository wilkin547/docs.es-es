---
description: "Más información sobre: BC30007: referencia necesaria para el ensamblado ' <assemblyname> ' que contiene la clase base ' <classname> '"
title: Es necesaria una referencia al ensamblado '<assemblyname>' que contenga la clase base '<classname>'
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: e6d4cf660453078d9a0f9825bc81bb990c1f55b9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456892"
---
# <a name="bc30007-reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a><span data-ttu-id="0ff15-103">BC30007: referencia necesaria para el ensamblado ' \<assemblyname> ' que contiene la clase base ' \<classname> '</span><span class="sxs-lookup"><span data-stu-id="0ff15-103">BC30007: Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'</span></span>

<span data-ttu-id="0ff15-104">Es necesaria una referencia al ensamblado ' \<assemblyname> ' que contiene la clase base ' \<classname> '.</span><span class="sxs-lookup"><span data-stu-id="0ff15-104">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="0ff15-105">Agregue una al proyecto.</span><span class="sxs-lookup"><span data-stu-id="0ff15-105">Add one to your project.</span></span>

 <span data-ttu-id="0ff15-106">La clase está definida en una biblioteca de vínculos dinámicos (DLL) o un ensamblado al que no se hace referencia directamente en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0ff15-106">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="0ff15-107">El compilador Visual Basic requiere una referencia para evitar la ambigüedad en caso de que la clase esté definida en más de una DLL o ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0ff15-107">The Visual Basic compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>

 <span data-ttu-id="0ff15-108">**Identificador de error:** BC30007</span><span class="sxs-lookup"><span data-stu-id="0ff15-108">**Error ID:** BC30007</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0ff15-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0ff15-109">To correct this error</span></span>

- <span data-ttu-id="0ff15-110">Incluya el nombre de la DLL o el ensamblado no referenciados en las referencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0ff15-110">Include the name of the unreferenced DLL or assembly in your project references.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ff15-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ff15-111">See also</span></span>

- [<span data-ttu-id="0ff15-112">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="0ff15-112">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="0ff15-113">Solucionar problemas de referencias rotas</span><span class="sxs-lookup"><span data-stu-id="0ff15-113">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
