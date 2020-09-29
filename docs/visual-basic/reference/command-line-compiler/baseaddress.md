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
ms.openlocfilehash: c794d1fc1c9d20e22ffa747e3175c846341ad8ad
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097766"
---
# <a name="-baseaddress"></a><span data-ttu-id="227f6-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="227f6-102">-baseaddress</span></span>

<span data-ttu-id="227f6-103">Especifica una dirección base predeterminada al crear un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="227f6-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="227f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="227f6-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="227f6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="227f6-105">Arguments</span></span>  
  
|<span data-ttu-id="227f6-106">Término</span><span class="sxs-lookup"><span data-stu-id="227f6-106">Term</span></span>|<span data-ttu-id="227f6-107">Definición</span><span class="sxs-lookup"><span data-stu-id="227f6-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="227f6-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="227f6-108">Required.</span></span> <span data-ttu-id="227f6-109">La dirección base del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="227f6-109">The base address for the DLL.</span></span> <span data-ttu-id="227f6-110">Esta dirección debe especificarse como un número hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="227f6-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="227f6-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="227f6-111">Remarks</span></span>  

 <span data-ttu-id="227f6-112">.NET Framework establece la dirección base predeterminada de un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="227f6-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="227f6-113">Tenga en cuenta que la palabra de orden inferior en esta dirección se redondea.</span><span class="sxs-lookup"><span data-stu-id="227f6-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="227f6-114">Por ejemplo, si se especifica 0x11110001, se redondea a 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="227f6-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="227f6-115">Para completar el proceso de firma de un archivo DLL, use la opción `–R` de la herramienta de nombre seguro (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="227f6-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="227f6-116">Esta opción se omite si el destino no es un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="227f6-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="227f6-117">Para establecer -baseaddress en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="227f6-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="227f6-118">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="227f6-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="227f6-119">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="227f6-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="227f6-120">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="227f6-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="227f6-121">3.  Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="227f6-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="227f6-122">4.  Modifique el valor en el cuadro **Dirección base del archivo DLL**.</span><span class="sxs-lookup"><span data-stu-id="227f6-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="227f6-123">**Nota:**      El cuadro **Dirección base del archivo DLL** es de solo lectura excepto si el destino es un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="227f6-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="227f6-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="227f6-124">See also</span></span>

- [<span data-ttu-id="227f6-125">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="227f6-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="227f6-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="227f6-126">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="227f6-127">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="227f6-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="227f6-128">[Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)</span><span class="sxs-lookup"><span data-stu-id="227f6-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
