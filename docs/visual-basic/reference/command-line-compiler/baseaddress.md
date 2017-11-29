---
title: /baseaddress
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8be88bf4834ca58b1fe708eb1ef7188c583fef0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="baseaddress"></a><span data-ttu-id="3e53f-102">/baseaddress</span><span class="sxs-lookup"><span data-stu-id="3e53f-102">/baseaddress</span></span>
<span data-ttu-id="3e53f-103">Especifica una dirección base predeterminada al crear un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="3e53f-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e53f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e53f-104">Syntax</span></span>  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="3e53f-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3e53f-105">Arguments</span></span>  
  
|<span data-ttu-id="3e53f-106">Término</span><span class="sxs-lookup"><span data-stu-id="3e53f-106">Term</span></span>|<span data-ttu-id="3e53f-107">Definición</span><span class="sxs-lookup"><span data-stu-id="3e53f-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="3e53f-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="3e53f-108">Required.</span></span> <span data-ttu-id="3e53f-109">La dirección base del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="3e53f-109">The base address for the DLL.</span></span> <span data-ttu-id="3e53f-110">Esta dirección debe especificarse como un número hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="3e53f-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e53f-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e53f-111">Remarks</span></span>  
 <span data-ttu-id="3e53f-112">La dirección base predeterminada para un archivo DLL se establece el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e53f-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="3e53f-113">Tenga en cuenta que la palabra de orden inferior de esta dirección se redondea.</span><span class="sxs-lookup"><span data-stu-id="3e53f-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="3e53f-114">Por ejemplo, si especifica 0 x 11110001, se redondea como 0 x 11110000.</span><span class="sxs-lookup"><span data-stu-id="3e53f-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="3e53f-115">Para completar el proceso de firma de un archivo DLL, utilice la `–R` opción de la herramienta de nombres seguros (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="3e53f-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="3e53f-116">Esta opción se omite si el destino no es un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="3e53f-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="3e53f-117">Para establecer /baseaddress en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3e53f-117">To set /baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="3e53f-118">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="3e53f-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3e53f-119">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3e53f-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="3e53f-120">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="3e53f-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="3e53f-121">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="3e53f-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="3e53f-122">3.  Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="3e53f-122">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="3e53f-123">4.  Modifique el valor en el **dirección base del archivo DLL:** cuadro.</span><span class="sxs-lookup"><span data-stu-id="3e53f-123">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="3e53f-124">**Nota:** el **dirección base del archivo DLL:** cuadro es de solo lectura, a menos que el destino es un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="3e53f-124">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e53f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e53f-125">See Also</span></span>  
 [<span data-ttu-id="3e53f-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3e53f-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="3e53f-127">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e53f-127">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="3e53f-128">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e53f-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="3e53f-129">Sn.exe (Herramienta de nombre seguro)</span><span class="sxs-lookup"><span data-stu-id="3e53f-129">Sn.exe (Strong Name Tool)</span></span>](https://msdn.microsoft.com/library/k5b5tt23)
