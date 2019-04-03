---
title: Desarrollo rápido de aplicaciones con My.Resources y My.Settings (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 4a9021af23200323397cc49fa1a44a0cc48b5a1d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816712"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="75a6c-102">Desarrollo rápido de aplicaciones con My.Resources y My.Settings (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75a6c-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>
<span data-ttu-id="75a6c-103">La `My.Resources` objeto proporciona acceso a recursos de la aplicación y le permite recuperar dinámicamente los recursos de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="75a6c-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="75a6c-104">Recuperar recursos</span><span class="sxs-lookup"><span data-stu-id="75a6c-104">Retrieving Resources</span></span>  
 <span data-ttu-id="75a6c-105">Un número de recursos, como cadenas, iconos, imágenes y archivos de audio se puede recuperar mediante el `My.Resources` objeto.</span><span class="sxs-lookup"><span data-stu-id="75a6c-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="75a6c-106">Por ejemplo, puede tener acceso a archivos de recursos específicos de la referencia cultural de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75a6c-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="75a6c-107">En el ejemplo siguiente se establece el icono del formulario en el icono denominado `Form1Icon` almacenados en el archivo de recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75a6c-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 <span data-ttu-id="75a6c-108">La `My.Resources` objeto expone sólo recursos globales.</span><span class="sxs-lookup"><span data-stu-id="75a6c-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="75a6c-109">No proporciona acceso a los archivos de recursos asociados con los formularios.</span><span class="sxs-lookup"><span data-stu-id="75a6c-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="75a6c-110">Debe tener acceso a los recursos de formulario desde el formulario.</span><span class="sxs-lookup"><span data-stu-id="75a6c-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="75a6c-111">De forma similar, la `My.Settings` objeto proporciona acceso a la configuración de la aplicación y permite almacenar y recuperar valores de propiedad y otra información para la aplicación de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="75a6c-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="75a6c-112">Para obtener más información, consulte [My.Resources (objeto)](../../../visual-basic/language-reference/objects/my-resources-object.md) y [My.Settings (objeto)](../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="75a6c-112">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75a6c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="75a6c-113">See also</span></span>

- [<span data-ttu-id="75a6c-114">My.Resources (objeto)</span><span class="sxs-lookup"><span data-stu-id="75a6c-114">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [<span data-ttu-id="75a6c-115">My.Settings (objeto)</span><span class="sxs-lookup"><span data-stu-id="75a6c-115">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="75a6c-116">Acceso a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="75a6c-116">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/index.md)
