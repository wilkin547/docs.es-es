---
title: Desarrollo rápido de aplicaciones con My.Resources y My.Settings
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: ce9a5bf76ba3132f58aa40227a145d8b5bf1591d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349263"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="f9f8e-102">Desarrollo rápido de aplicaciones con My.Resources y My.Settings (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9f8e-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>

<span data-ttu-id="f9f8e-103">El objeto `My.Resources` da acceso a los recursos de la aplicación y permite recuperar recursos de la aplicación dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="f9f8e-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="f9f8e-104">Recuperar recursos</span><span class="sxs-lookup"><span data-stu-id="f9f8e-104">Retrieving Resources</span></span>  

 <span data-ttu-id="f9f8e-105">Con el objeto `My.Resources` se pueden recuperar una serie de recursos, como archivos de audio, iconos, imágenes y cadenas.</span><span class="sxs-lookup"><span data-stu-id="f9f8e-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="f9f8e-106">Por ejemplo, permite acceder a los archivos de recursos específicos de la referencia cultural de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9f8e-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="f9f8e-107">En el siguiente ejemplo se establece el icono del formulario en el icono denominado `Form1Icon` que está almacenado en el archivo de recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9f8e-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 <span data-ttu-id="f9f8e-108">El objeto `My.Resources` expone solo recursos globales.</span><span class="sxs-lookup"><span data-stu-id="f9f8e-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="f9f8e-109">No da acceso a los archivos de recursos asociados a los formularios.</span><span class="sxs-lookup"><span data-stu-id="f9f8e-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="f9f8e-110">Para acceder a los recursos de formulario, hay que hacerlo desde el formulario.</span><span class="sxs-lookup"><span data-stu-id="f9f8e-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="f9f8e-111">De forma similar, el objeto `My.Settings` da acceso a la configuración de la aplicación y permite almacenar y recuperar dinámicamente la configuración de propiedades y otra información de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9f8e-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="f9f8e-112">Para más información, vea [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) y [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="f9f8e-112">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9f8e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9f8e-113">See also</span></span>

- [<span data-ttu-id="f9f8e-114">My.Resources (objeto)</span><span class="sxs-lookup"><span data-stu-id="f9f8e-114">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [<span data-ttu-id="f9f8e-115">My.Settings (objeto)</span><span class="sxs-lookup"><span data-stu-id="f9f8e-115">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="f9f8e-116">Acceso a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f9f8e-116">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/index.md)
