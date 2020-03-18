---
title: Procedimiento para cambiar la configuración del usuario
ms.date: 07/20/2015
helpviewer_keywords:
- user settings [Visual Basic], changing in Visual Basic
- user settings
- My.Settings object [Visual Basic], changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
ms.openlocfilehash: d24b6d239c894788ce67b0723b4bf034050bf307
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74329626"
---
# <a name="how-to-change-user-settings-in-visual-basic"></a><span data-ttu-id="af065-102">Procedimiento para cambiar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="af065-102">How to: Change User Settings in Visual Basic</span></span>

<span data-ttu-id="af065-103">Puede cambiar una configuración de usuario mediante la asignación de un nuevo valor a la propiedad de la configuración en el objeto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="af065-103">You can change a user setting by assigning a new value to the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="af065-104">El objeto `My.Settings` expone cada configuración como una propiedad.</span><span class="sxs-lookup"><span data-stu-id="af065-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="af065-105">El nombre de propiedad es el mismo que el nombre de la configuración y el tipo de propiedad es el mismo que el tipo de configuración.</span><span class="sxs-lookup"><span data-stu-id="af065-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="af065-106">El **ámbito** de la configuración determina si la propiedad es de solo lectura: La propiedad de una configuración con ámbito **Aplicación** es de solo lectura, mientras que la propiedad de una configuración con ámbito **Usuario** es de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="af065-106">The setting's **Scope** determines if the property is read-only: The property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="af065-107">Para más información, consulte [My.Settings (Objeto)](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="af065-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af065-108">Aunque se pueden cambiar y guardar los valores de configuraciones con ámbito de usuario en tiempo de ejecución, las configuraciones con ámbito de aplicación son de solo lectura y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="af065-108">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="af065-109">Las configuraciones con ámbito de aplicación se pueden cambiar en el momento de crear la aplicación mediante el **Diseñador de proyectos** o a través del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="af065-109">You can change application-scope settings when you create the application by using the **Project Designer** or by editing the application's configuration file.</span></span> <span data-ttu-id="af065-110">Para obtener más información, consulte [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="af065-110">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af065-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af065-111">Example</span></span>  

 <span data-ttu-id="af065-112">En este ejemplo se cambia el valor de la configuración de usuario `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="af065-112">This example changes the value of the `Nickname` user setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#7)]  
  
 <span data-ttu-id="af065-113">Para que este ejemplo funcione, la aplicación debe tener una configuración de usuario `Nickname`, de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="af065-113">For this example to work, your application must have a `Nickname` user setting, of type `String`.</span></span>  
  
 <span data-ttu-id="af065-114">La aplicación guarda la configuración del usuario cuando se cierra.</span><span class="sxs-lookup"><span data-stu-id="af065-114">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="af065-115">Para guardar la configuración inmediatamente, llame al método `My.Settings.Save`.</span><span class="sxs-lookup"><span data-stu-id="af065-115">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="af065-116">Para obtener más información, vea [Cómo: Conservar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span><span class="sxs-lookup"><span data-stu-id="af065-116">For more information, see [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af065-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="af065-117">See also</span></span>

- [<span data-ttu-id="af065-118">My.Settings (objeto)</span><span class="sxs-lookup"><span data-stu-id="af065-118">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="af065-119">Cómo: Leer la configuración de la aplicación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="af065-119">How to: Read Application Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="af065-120">Cómo: Conservar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="af065-120">How to: Persist User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="af065-121">Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="af065-121">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="af065-122">Administrar la configuración de la aplicación (.NET)</span><span class="sxs-lookup"><span data-stu-id="af065-122">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
