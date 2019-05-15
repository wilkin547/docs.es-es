---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: e8dfe95ef3385635f5839ecc96047911544a256e
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591453"
---
# <a name="-baseaddress"></a><span data-ttu-id="f2312-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="f2312-102">-baseaddress</span></span>
<span data-ttu-id="f2312-103">Especifica una dirección base predeterminada al crear un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="f2312-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2312-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2312-104">Syntax</span></span>  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="f2312-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f2312-105">Arguments</span></span>  
  
|<span data-ttu-id="f2312-106">Término</span><span class="sxs-lookup"><span data-stu-id="f2312-106">Term</span></span>|<span data-ttu-id="f2312-107">Definición</span><span class="sxs-lookup"><span data-stu-id="f2312-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="f2312-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f2312-108">Required.</span></span> <span data-ttu-id="f2312-109">La dirección base del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="f2312-109">The base address for the DLL.</span></span> <span data-ttu-id="f2312-110">Esta dirección debe especificarse como un número hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="f2312-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2312-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2312-111">Remarks</span></span>  
 <span data-ttu-id="f2312-112">La dirección base predeterminada para un archivo DLL se establece por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f2312-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="f2312-113">Tenga en cuenta que la palabra de orden inferior en esta dirección se redondea.</span><span class="sxs-lookup"><span data-stu-id="f2312-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="f2312-114">Por ejemplo, si especifica 0 x 11110001, se redondea a 0 x 11110000.</span><span class="sxs-lookup"><span data-stu-id="f2312-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="f2312-115">Para completar el proceso de firma de un archivo DLL, utilice el `–R` opción de la herramienta nombre seguro (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="f2312-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="f2312-116">Esta opción se omite si el destino no es un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="f2312-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="f2312-117">Para establecer - baseaddress en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f2312-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="f2312-118">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="f2312-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f2312-119">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f2312-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="f2312-120">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="f2312-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="f2312-121">3.  Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="f2312-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="f2312-122">4.  Modifique el valor en el **dirección base del archivo DLL:** cuadro.</span><span class="sxs-lookup"><span data-stu-id="f2312-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="f2312-123">**Nota:**      El **dirección base del archivo DLL:** cuadro es de solo lectura a menos que el destino es un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="f2312-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2312-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2312-124">See also</span></span>

- [<span data-ttu-id="f2312-125">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f2312-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f2312-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2312-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="f2312-127">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2312-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="f2312-128">[Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="f2312-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
