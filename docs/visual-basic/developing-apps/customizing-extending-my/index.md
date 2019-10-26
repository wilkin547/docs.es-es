---
title: Personalizar proyectos y ampliar My con Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 06ca80b9-1192-4eb5-8537-8ef5edfb9be0
ms.openlocfilehash: 97933a9d014a54d5b6e333090cddccace99fcc3c
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960944"
---
# <a name="customizing-projects-and-extending-my-with-visual-basic"></a><span data-ttu-id="f7390-102">Personalizar proyectos y ampliar My con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7390-102">Customizing Projects and Extending My with Visual Basic</span></span>

<span data-ttu-id="f7390-103">Puede personalizar las plantillas de proyecto para proporcionar objetos de `My` adicionales.</span><span class="sxs-lookup"><span data-stu-id="f7390-103">You can customize project templates to provide additional `My` objects.</span></span> <span data-ttu-id="f7390-104">Esto facilita a otros desarrolladores la búsqueda y el uso de los objetos.</span><span class="sxs-lookup"><span data-stu-id="f7390-104">This makes it easy for other developers to find and use your objects.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f7390-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f7390-105">In this section</span></span>

- [<span data-ttu-id="f7390-106">Extender el espacio de nombres My en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7390-106">Extending the My Namespace in Visual Basic</span></span>](extending-the-my-namespace.md)  
 <span data-ttu-id="f7390-107">Describe cómo agregar miembros personalizados y valores al espacio de nombres `My` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f7390-107">Describes how to add custom members and values to the `My` namespace in Visual Basic.</span></span>
- [<span data-ttu-id="f7390-108">Empaquetado e implementación de extensiones de My personalizadas</span><span class="sxs-lookup"><span data-stu-id="f7390-108">Packaging and Deploying Custom My Extensions</span></span>](packaging-and-deploying-custom-my-extensions.md)  
 <span data-ttu-id="f7390-109">Describe cómo publicar extensiones de espacio de nombres de `My` personalizado mediante el uso de plantillas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f7390-109">Describes how to publish custom `My` namespace extensions by using Visual Studio templates.</span></span>
- [<span data-ttu-id="f7390-110">Extensión del modelo de la aplicación de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7390-110">Extending the Visual Basic Application Model</span></span>](extending-the-visual-basic-application-model.md)  
 <span data-ttu-id="f7390-111">Describe cómo especificar sus propias extensiones para el modelo de aplicación mediante la invalidación de miembros de la clase <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>.</span><span class="sxs-lookup"><span data-stu-id="f7390-111">Describes how to specify your own extensions to the application model by overriding members of the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class.</span></span>
- [<span data-ttu-id="f7390-112">Personalización de los objetos que están disponibles en My</span><span class="sxs-lookup"><span data-stu-id="f7390-112">Customizing Which Objects are Available in My</span></span>](customizing-which-objects-are-available-in-my.md)  
 <span data-ttu-id="f7390-113">Describe cómo controlar qué objetos de `My` se habilitan estableciendo la constante de compilación condicional de \_del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f7390-113">Describes how to control which `My` objects are enabled by setting your project's \_MYTYPE conditional-compilation constant.</span></span>

## <a name="related-sections"></a><span data-ttu-id="f7390-114">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="f7390-114">Related sections</span></span>

- [<span data-ttu-id="f7390-115">Desarrollo con la función My</span><span class="sxs-lookup"><span data-stu-id="f7390-115">Development with My</span></span>](../development-with-my/index.md)  
 <span data-ttu-id="f7390-116">Describe qué objetos `My` están disponibles de forma predeterminada en distintos tipos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f7390-116">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="f7390-117">Información general sobre el modelo de aplicaciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7390-117">Overview of the Visual Basic Application Model</span></span>](../development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="f7390-118">Describe el modelo de Visual Basic para controlar el comportamiento de las aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f7390-118">Describes Visual Basic's model for controlling the behavior of Windows Forms applications.</span></span>
- [<span data-ttu-id="f7390-119">Cómo My depende del tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="f7390-119">How My Depends on Project Type</span></span>](../development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="f7390-120">Describe qué objetos `My` están disponibles de forma predeterminada en distintos tipos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f7390-120">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="f7390-121">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="f7390-121">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="f7390-122">Describe cómo el compilador utiliza la compilación condicional para seleccionar secciones de código determinadas para compilar y excluir otras secciones.</span><span class="sxs-lookup"><span data-stu-id="f7390-122">Discusses how the compiler uses conditional-compilation to select particular sections of code to compile and exclude other sections.</span></span>
- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <span data-ttu-id="f7390-123">Describe el objeto de `My` que proporciona propiedades, métodos y eventos relacionados con la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="f7390-123">Describes the `My` object that provides properties, methods, and events related to the current application.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7390-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7390-124">See also</span></span>

- [<span data-ttu-id="f7390-125">Desarrollo de aplicaciones con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7390-125">Developing Applications with Visual Basic</span></span>](../index.md)
