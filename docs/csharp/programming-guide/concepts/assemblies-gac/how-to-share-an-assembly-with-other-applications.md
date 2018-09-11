---
title: 'Cómo: Compartir un ensamblado con otras aplicaciones (C#)'
ms.date: 07/20/2015
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: a5b20061c759fd914193f24aa123317f13d31dce
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266474"
---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a><span data-ttu-id="3b541-102">Cómo: Compartir un ensamblado con otras aplicaciones (C#)</span><span class="sxs-lookup"><span data-stu-id="3b541-102">How to: Share an Assembly with Other Applications (C#)</span></span>
<span data-ttu-id="3b541-103">Los ensamblados pueden ser privados o compartidos: de forma predeterminada, la mayoría de los programas sencillos constan de un ensamblado privado porque no se diseñaron para ser usados por otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3b541-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="3b541-104">Para compartir un ensamblado con otras aplicaciones, debe colocarse en la [caché global de ensamblados](../../../../framework/app-domains/gac.md) (GAC).</span><span class="sxs-lookup"><span data-stu-id="3b541-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="3b541-105">Compartir un ensamblado</span><span class="sxs-lookup"><span data-stu-id="3b541-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="3b541-106">Cree el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3b541-106">Create your assembly.</span></span> <span data-ttu-id="3b541-107">Para obtener más información, vea [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md) (Crear ensamblados).</span><span class="sxs-lookup"><span data-stu-id="3b541-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="3b541-108">Asigne un nombre seguro al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3b541-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="3b541-109">Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="3b541-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="3b541-110">Asigne la información de versión al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3b541-110">Assign version information to your assembly.</span></span> <span data-ttu-id="3b541-111">Para obtener más información, vea [Versiones de los ensamblados](../../../../../docs/framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="3b541-111">For more information, see [Assembly Versioning](../../../../../docs/framework/app-domains/assembly-versioning.md).</span></span>  
  
4.  <span data-ttu-id="3b541-112">Agregue el ensamblado a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3b541-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="3b541-113">Para obtener más información, vea [Cómo: Instalar un ensamblado en la memoria caché global de ensamblados](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="3b541-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="3b541-114">Obtenga acceso a los tipos contenidos en el ensamblado desde las otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3b541-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="3b541-115">Para obtener más información, vea [Cómo: Hacer referencia a un ensamblado con nombre seguro](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="3b541-115">For more information, see [How to: Reference a Strong-Named Assembly](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b541-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b541-116">See Also</span></span>

- [<span data-ttu-id="3b541-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3b541-117">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3b541-118">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="3b541-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
