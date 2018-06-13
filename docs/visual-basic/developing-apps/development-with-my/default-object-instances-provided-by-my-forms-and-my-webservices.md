---
title: Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 421995684201ec48d5e8aff9b0ed7640efd1e4b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582667"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="665d1-102">Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="665d1-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>
<span data-ttu-id="665d1-103">El [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) y [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objetos proporcionan acceso a formularios, orígenes de datos y servicios Web XML utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="665d1-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="665d1-104">Para ello, proporcionan colecciones de *instancias predeterminadas* de cada uno de estos objetos.</span><span class="sxs-lookup"><span data-stu-id="665d1-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="665d1-105">Instancias predeterminadas</span><span class="sxs-lookup"><span data-stu-id="665d1-105">Default Instances</span></span>  
 <span data-ttu-id="665d1-106">Una instancia predeterminada es una instancia de la clase que se proporciona en tiempo de ejecución y no necesita ser declara y crea una instancia mediante el `Dim` y `New` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="665d1-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="665d1-107">En el ejemplo siguiente se muestra cómo podría haber declara y crea una instancia de una instancia de un <xref:System.Windows.Forms.Form> clase llamada `Form1`, y cómo ahora se puede obtener una instancia predeterminada de este <xref:System.Windows.Forms.Form> a través de la clase `My.Forms`.</span><span class="sxs-lookup"><span data-stu-id="665d1-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 <span data-ttu-id="665d1-108">El `My.Forms` object devuelve una colección de instancias predeterminadas para cada `Form` clase que exista en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="665d1-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="665d1-109">De forma similar, `My.WebServices` proporciona una instancia predeterminada de la clase de proxy para cada servicio Web que ha creado una referencia a en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="665d1-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="665d1-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="665d1-110">See Also</span></span>  
 [<span data-ttu-id="665d1-111">My.Forms (objeto)</span><span class="sxs-lookup"><span data-stu-id="665d1-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [<span data-ttu-id="665d1-112">My.WebServices (objeto)</span><span class="sxs-lookup"><span data-stu-id="665d1-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [<span data-ttu-id="665d1-113">Cómo My depende del tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="665d1-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
