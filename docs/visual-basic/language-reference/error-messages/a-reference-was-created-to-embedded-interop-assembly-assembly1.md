---
title: Se creó una referencia al ensamblado de interoperabilidad '<assembly1>' incrustado debido a una referencia indirecta a dicho ensamblado desde el ensamblado '<assembly2>'
ms.date: 07/20/2015
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
ms.openlocfilehash: c0b4f56e3d1613486dd1198976557831ce657e1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837551"
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-assembly1-because-of-an-indirect-reference-to-that-assembly-from-assembly-assembly2"></a><span data-ttu-id="20d66-102">Se creó una referencia al ensamblado de interoperabilidad incrustado '\<ensamblado1 >' debido a una referencia indirecta a dicho ensamblado desde el ensamblado '\<ensamblado2 >'</span><span class="sxs-lookup"><span data-stu-id="20d66-102">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'</span></span>
<span data-ttu-id="20d66-103">Se ha creado una referencia al ensamblado de interoperabilidad "\<ensamblado1>" insertado debido a una referencia indirecta a dicho ensamblado desde el ensamblado "\<ensamblado2>".</span><span class="sxs-lookup"><span data-stu-id="20d66-103">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'.</span></span> <span data-ttu-id="20d66-104">Considere cambiar la propiedad "Incrustar tipos de interoperabilidad" en uno de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="20d66-104">Consider changing the 'Embed Interop Types' property on either assembly.</span></span>  
  
 <span data-ttu-id="20d66-105">Ha agregado una referencia a un ensamblado (ensamblado1) cuya propiedad `Embed Interop Types` está establecida en `True`.</span><span class="sxs-lookup"><span data-stu-id="20d66-105">You have added a reference to an assembly (assembly1) that has the `Embed Interop Types` property set to `True`.</span></span> <span data-ttu-id="20d66-106">Esto indica al compilador que incruste la información de tipo de interoperabilidad desde este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="20d66-106">This instructs the compiler to embed interop type information from that assembly.</span></span> <span data-ttu-id="20d66-107">Sin embargo, el compilador no puede incrustar información de tipo de interoperabilidad desde este ese ensamblado porque otro ensamblado al que ha hecho referencia (ensamblado2) también hace referencia a este ensamblado (ensamblado1) y tiene la propiedad `Embed Interop Types` establecida en `False`.</span><span class="sxs-lookup"><span data-stu-id="20d66-107">However, the compiler cannot embed interop type information from that assembly because another assembly that you have referenced (assembly2) also references that assembly (assembly1) and has the `Embed Interop Types` property set to `False`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20d66-108">Para el compilador de línea de comandos, el establecimiento de la propiedad `Embed Interop Types` de una referencia a ensamblado en `True` equivale a hacer referencia al ensamblado utilizando la opción `/link`.</span><span class="sxs-lookup"><span data-stu-id="20d66-108">Setting the `Embed Interop Types` property on an assembly reference to `True` is equivalent to referencing the assembly by using the `/link` option for the command-line compiler.</span></span>  
  
 <span data-ttu-id="20d66-109">**Identificador de error:** BC40059</span><span class="sxs-lookup"><span data-stu-id="20d66-109">**Error ID:** BC40059</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="20d66-110">Para resolver esta advertencia</span><span class="sxs-lookup"><span data-stu-id="20d66-110">To address this warning</span></span>  
  
-   <span data-ttu-id="20d66-111">Para incrustar información de tipo de interoperabilidad para ambos ensamblados, establezca la propiedad `Embed Interop Types` de todas las referencias a ensamblado1 en `True`.</span><span class="sxs-lookup"><span data-stu-id="20d66-111">To embed interop type information for both assemblies, set the `Embed Interop Types` property on all references to assembly1 to `True`.</span></span>  
  
-   <span data-ttu-id="20d66-112">Para quitar la advertencia, puede establecer la propiedad `Embed Interop Types` de ensamblado1 en `False`.</span><span class="sxs-lookup"><span data-stu-id="20d66-112">To remove the warning, you can set the `Embed Interop Types` property of assembly1 to `False`.</span></span> <span data-ttu-id="20d66-113">En este caso, se proporciona información de tipo de interoperabilidad por un ensamblado de interoperabilidad primario (PIA).</span><span class="sxs-lookup"><span data-stu-id="20d66-113">In this case, interop type information is provided by a primary interop assembly (PIA).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20d66-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="20d66-114">See also</span></span>

- [<span data-ttu-id="20d66-115">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20d66-115">/link (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/link.md)
- <span data-ttu-id="20d66-116">[Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="20d66-116">[Interoperating with Unmanaged Code](../../../framework/interop/index.md)</span></span>
