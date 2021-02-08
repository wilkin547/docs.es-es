---
description: 'Más información acerca de: Directiva de #Region'
title: '#Directiva Region'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: 4ba1645cfc51a69d39e6a60b5ea236dd65883e1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797229"
---
# <a name="region-directive"></a><span data-ttu-id="04793-103">#Region (Directiva)</span><span class="sxs-lookup"><span data-stu-id="04793-103">#Region Directive</span></span>

<span data-ttu-id="04793-104">Contrae y oculta secciones de código en archivos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="04793-104">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04793-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04793-105">Syntax</span></span>  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="04793-106">Partes</span><span class="sxs-lookup"><span data-stu-id="04793-106">Parts</span></span>  
  
|<span data-ttu-id="04793-107">Término</span><span class="sxs-lookup"><span data-stu-id="04793-107">Term</span></span>|<span data-ttu-id="04793-108">Definición</span><span class="sxs-lookup"><span data-stu-id="04793-108">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="04793-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="04793-109">Required.</span></span> <span data-ttu-id="04793-110">Cadena que actúa como título de una región cuando esta se contrae.</span><span class="sxs-lookup"><span data-stu-id="04793-110">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="04793-111">Las regiones están contraídas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="04793-111">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="04793-112">Finaliza el bloque `#Region`.</span><span class="sxs-lookup"><span data-stu-id="04793-112">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04793-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="04793-113">Remarks</span></span>  

 <span data-ttu-id="04793-114">La directiva `#Region` permite especificar un bloque de código que se puede expandir o contraer cuando se usa la característica de esquematización del Editor de código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04793-114">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="04793-115">Puede colocar, o *anidar*, regiones en otras regiones para agrupar regiones similares.</span><span class="sxs-lookup"><span data-stu-id="04793-115">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04793-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04793-116">Example</span></span>  

 <span data-ttu-id="04793-117">En este ejemplo se usa la directiva `#Region`.</span><span class="sxs-lookup"><span data-stu-id="04793-117">This example uses the `#Region` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="04793-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="04793-118">See also</span></span>

- [<span data-ttu-id="04793-119">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="04793-119">#If...Then...#Else Directives</span></span>](if-then-else-directives.md)
- [<span data-ttu-id="04793-120">Esquematización</span><span class="sxs-lookup"><span data-stu-id="04793-120">Outlining</span></span>](/visualstudio/ide/outlining)
- [<span data-ttu-id="04793-121">Procedimiento Contracción y ocultación de secciones de código</span><span class="sxs-lookup"><span data-stu-id="04793-121">How to: Collapse and Hide Sections of Code</span></span>](../../programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
