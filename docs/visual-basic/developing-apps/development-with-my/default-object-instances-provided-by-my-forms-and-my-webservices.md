---
title: Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 847724450ee2bc8bc591371f71171e8ba4ed9337
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411745"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="e146a-102">Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e146a-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>

<span data-ttu-id="e146a-103">Los objetos [My.Forms](../../language-reference/objects/my-forms-object.md) y [My.WebServices](../../language-reference/objects/my-webservices-object.md) proporcionan acceso a formularios, orígenes de datos y servicios web XML utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e146a-103">The [My.Forms](../../language-reference/objects/my-forms-object.md) and [My.WebServices](../../language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="e146a-104">Para ello, proporcionan colecciones de *instancias predeterminadas* de cada uno de estos objetos.</span><span class="sxs-lookup"><span data-stu-id="e146a-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="e146a-105">Instancias predeterminadas</span><span class="sxs-lookup"><span data-stu-id="e146a-105">Default Instances</span></span>  

 <span data-ttu-id="e146a-106">Una instancia predeterminada es una instancia de la clase proporcionada por el runtime y que no es necesario declarar y ni crear una instancia mediante las instrucciones `Dim` y `New`.</span><span class="sxs-lookup"><span data-stu-id="e146a-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="e146a-107">En el ejemplo siguiente se muestra cómo se podría haber declarado y creado una instancia de una clase <xref:System.Windows.Forms.Form> denominada `Form1` y cómo ahora se puede obtener una instancia predeterminada de esta clase <xref:System.Windows.Forms.Form> a través de `My.Forms`.</span><span class="sxs-lookup"><span data-stu-id="e146a-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="e146a-108">El objeto `My.Forms` devuelve una colección de instancias predeterminadas para todas las clases `Form` que existen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e146a-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="e146a-109">Del mismo modo, `My.WebServices` proporciona una instancia predeterminada de la clase de proxy para cada servicio web para el que se haya creado una referencia en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e146a-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e146a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e146a-110">See also</span></span>

- [<span data-ttu-id="e146a-111">My.Forms (objeto)</span><span class="sxs-lookup"><span data-stu-id="e146a-111">My.Forms Object</span></span>](../../language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="e146a-112">My.WebServices (objeto)</span><span class="sxs-lookup"><span data-stu-id="e146a-112">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="e146a-113">Cómo My depende del tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="e146a-113">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)
