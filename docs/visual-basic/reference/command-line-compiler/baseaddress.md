---
description: Más información sobre -baseaddress
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
ms.openlocfilehash: eaa2992c126ebb83b20cfdbef3ab995a30ee25fd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468322"
---
# <a name="-baseaddress"></a><span data-ttu-id="ad82d-103">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="ad82d-103">-baseaddress</span></span>

<span data-ttu-id="ad82d-104">Especifica una dirección base predeterminada al crear un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="ad82d-104">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad82d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad82d-105">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="ad82d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ad82d-106">Arguments</span></span>  
  
|<span data-ttu-id="ad82d-107">Término</span><span class="sxs-lookup"><span data-stu-id="ad82d-107">Term</span></span>|<span data-ttu-id="ad82d-108">Definición</span><span class="sxs-lookup"><span data-stu-id="ad82d-108">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="ad82d-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad82d-109">Required.</span></span> <span data-ttu-id="ad82d-110">La dirección base del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="ad82d-110">The base address for the DLL.</span></span> <span data-ttu-id="ad82d-111">Esta dirección debe especificarse como un número hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="ad82d-111">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad82d-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad82d-112">Remarks</span></span>  

 <span data-ttu-id="ad82d-113">.NET Framework establece la dirección base predeterminada de un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="ad82d-113">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="ad82d-114">Tenga en cuenta que la palabra de orden inferior en esta dirección se redondea.</span><span class="sxs-lookup"><span data-stu-id="ad82d-114">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="ad82d-115">Por ejemplo, si se especifica 0x11110001, se redondea a 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="ad82d-115">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="ad82d-116">Para completar el proceso de firma de un archivo DLL, use la opción `–R` de la herramienta de nombre seguro (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="ad82d-116">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="ad82d-117">Esta opción se omite si el destino no es un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="ad82d-117">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="ad82d-118">Para establecer -baseaddress en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ad82d-118">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="ad82d-119">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="ad82d-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ad82d-120">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ad82d-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="ad82d-121">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="ad82d-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="ad82d-122">3.  Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="ad82d-122">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="ad82d-123">4.  Modifique el valor en el cuadro **Dirección base del archivo DLL**.</span><span class="sxs-lookup"><span data-stu-id="ad82d-123">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="ad82d-124">**Nota:**      El cuadro **Dirección base del archivo DLL** es de solo lectura excepto si el destino es un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="ad82d-124">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad82d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad82d-125">See also</span></span>

- [<span data-ttu-id="ad82d-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad82d-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ad82d-127">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad82d-127">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="ad82d-128">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad82d-128">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="ad82d-129">[Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)</span><span class="sxs-lookup"><span data-stu-id="ad82d-129">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
