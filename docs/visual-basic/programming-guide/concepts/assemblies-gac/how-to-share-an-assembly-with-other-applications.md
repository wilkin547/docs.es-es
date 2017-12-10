---
title: "Cómo: compartir un ensamblado con otras aplicaciones (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0ad7a3f2ee82d0a582e755035448d565a9a8cb9d
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="33c1d-102">Cómo: compartir un ensamblado con otras aplicaciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33c1d-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="33c1d-103">Los ensamblados pueden ser privados o compartidos: de forma predeterminada, la mayoría de los programas sencillos constan de un ensamblado privado porque no se diseñaron para ser usados por otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="33c1d-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="33c1d-104">Para compartir un ensamblado con otras aplicaciones, debe colocarse en la [caché global de ensamblados](../../../../framework/app-domains/gac.md) (GAC).</span><span class="sxs-lookup"><span data-stu-id="33c1d-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="33c1d-105">Compartir un ensamblado</span><span class="sxs-lookup"><span data-stu-id="33c1d-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="33c1d-106">Cree el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="33c1d-106">Create your assembly.</span></span> <span data-ttu-id="33c1d-107">Para obtener más información, vea [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md) (Crear ensamblados).</span><span class="sxs-lookup"><span data-stu-id="33c1d-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="33c1d-108">Asigne un nombre seguro al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="33c1d-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="33c1d-109">Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="33c1d-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="33c1d-110">Asigne la información de versión al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="33c1d-110">Assign version information to your assembly.</span></span> <span data-ttu-id="33c1d-111">Para obtener más información, vea [Versiones de los ensamblados](../../../../../docs/framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="33c1d-111">For more information, see [Assembly Versioning](../../../../../docs/framework/app-domains/assembly-versioning.md).</span></span>  
  
4.  <span data-ttu-id="33c1d-112">Agregue el ensamblado a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="33c1d-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="33c1d-113">Para obtener más información, vea [Cómo: Instalar un ensamblado en la memoria caché global de ensamblados](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="33c1d-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="33c1d-114">Obtenga acceso a los tipos contenidos en el ensamblado desde las otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="33c1d-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="33c1d-115">Para obtener más información, vea [Cómo: Hacer referencia a un ensamblado con nombre seguro](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span><span class="sxs-lookup"><span data-stu-id="33c1d-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c1d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="33c1d-116">See Also</span></span>  
 <span data-ttu-id="33c1d-117">[Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md) [ensamblados y caché Global de ensamblados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span><span class="sxs-lookup"><span data-stu-id="33c1d-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span></span>  
 [<span data-ttu-id="33c1d-118">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="33c1d-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
