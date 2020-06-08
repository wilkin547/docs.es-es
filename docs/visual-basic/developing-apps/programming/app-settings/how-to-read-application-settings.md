---
title: Procedimiento para leer la configuración de la aplicación
ms.date: 07/20/2015
helpviewer_keywords:
- reading application settings
- My.Settings object [Visual Basic], reading application settings
- application settings [Visual Basic], reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
ms.openlocfilehash: 9b326341c54d652479776e3ab93a2b140f4531e0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410145"
---
# <a name="how-to-read-application-settings-in-visual-basic"></a><span data-ttu-id="c9fc0-102">Procedimiento para leer la configuración de la aplicación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9fc0-102">How to: Read Application Settings in Visual Basic</span></span>

<span data-ttu-id="c9fc0-103">Puede leer la configuración de un usuario accediendo a la propiedad de configuración del objeto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="c9fc0-103">You can read a user setting by accessing the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="c9fc0-104">El objeto `My.Settings` expone cada configuración como una propiedad.</span><span class="sxs-lookup"><span data-stu-id="c9fc0-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="c9fc0-105">El nombre de propiedad es el mismo que el nombre de la configuración y el tipo de propiedad es el mismo que el tipo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c9fc0-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="c9fc0-106">El **Ámbito** de la configuración indica si la propiedad es de solo lectura. La propiedad de una configuración con ámbito **Aplicación** es de solo lectura, mientras que la propiedad de una configuración con ámbito **Usuario** es de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="c9fc0-106">The setting's **Scope** indicates if the property is read-only; the property for an **Application** scope setting is read-only, while the property for a **User** scope setting is read-write.</span></span> <span data-ttu-id="c9fc0-107">Para más información, consulte [My.Settings (Objeto)](../../../language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="c9fc0-107">For more information, see [My.Settings Object](../../../language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9fc0-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9fc0-108">Example</span></span>  

 <span data-ttu-id="c9fc0-109">En este ejemplo se muestra el valor de la configuración `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="c9fc0-109">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="c9fc0-110">Para que este ejemplo funcione, la aplicación debe tener una configuración `Nickname` de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="c9fc0-110">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span> <span data-ttu-id="c9fc0-111">Para obtener más información, consulte [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="c9fc0-111">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9fc0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9fc0-112">See also</span></span>

- [<span data-ttu-id="c9fc0-113">My.Settings (objeto)</span><span class="sxs-lookup"><span data-stu-id="c9fc0-113">My.Settings Object</span></span>](../../../language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="c9fc0-114">Cómo: Cambiar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9fc0-114">How to: Change User Settings in Visual Basic</span></span>](how-to-change-user-settings.md)
- [<span data-ttu-id="c9fc0-115">Cómo: Conservar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9fc0-115">How to: Persist User Settings in Visual Basic</span></span>](how-to-persist-user-settings.md)
- [<span data-ttu-id="c9fc0-116">Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9fc0-116">How to: Create Property Grids for User Settings in Visual Basic</span></span>](how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="c9fc0-117">Administrar la configuración de la aplicación (.NET)</span><span class="sxs-lookup"><span data-stu-id="c9fc0-117">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
