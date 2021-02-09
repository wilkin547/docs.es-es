---
description: 'Más información acerca de: Procedimiento: para cambiar la configuración del usuario en Visual Basic'
title: Procedimiento para cambiar la configuración del usuario
ms.date: 07/20/2015
helpviewer_keywords:
- user settings [Visual Basic], changing in Visual Basic
- user settings
- My.Settings object [Visual Basic], changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
ms.openlocfilehash: 3877c9fadbf1b5b79470dc9ad41fbaf8123e6770
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797866"
---
# <a name="how-to-change-user-settings-in-visual-basic"></a><span data-ttu-id="45fd0-103">Cómo: Cambiar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45fd0-103">How to: Change User Settings in Visual Basic</span></span>

<span data-ttu-id="45fd0-104">Puede cambiar una configuración de usuario mediante la asignación de un nuevo valor a la propiedad de la configuración en el objeto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="45fd0-104">You can change a user setting by assigning a new value to the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="45fd0-105">El objeto `My.Settings` expone cada configuración como una propiedad.</span><span class="sxs-lookup"><span data-stu-id="45fd0-105">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="45fd0-106">El nombre de propiedad es el mismo que el nombre de la configuración y el tipo de propiedad es el mismo que el tipo de configuración.</span><span class="sxs-lookup"><span data-stu-id="45fd0-106">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="45fd0-107">El **ámbito** de la configuración determina si la propiedad es de solo lectura: La propiedad de una configuración con ámbito **Aplicación** es de solo lectura, mientras que la propiedad de una configuración con ámbito **Usuario** es de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="45fd0-107">The setting's **Scope** determines if the property is read-only: The property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="45fd0-108">Para obtener más información, vea [My.Settings (Objeto)](../../../language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="45fd0-108">For more information, see [My.Settings Object](../../../language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="45fd0-109">Aunque se pueden cambiar y guardar los valores de configuraciones con ámbito de usuario en tiempo de ejecución, las configuraciones con ámbito de aplicación son de solo lectura y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="45fd0-109">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="45fd0-110">Las configuraciones con ámbito de aplicación se pueden cambiar en el momento de crear la aplicación mediante el **Diseñador de proyectos** o a través del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45fd0-110">You can change application-scope settings when you create the application by using the **Project Designer** or by editing the application's configuration file.</span></span> <span data-ttu-id="45fd0-111">Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="45fd0-111">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="45fd0-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45fd0-112">Example</span></span>  

 <span data-ttu-id="45fd0-113">En este ejemplo se cambia el valor de la configuración de usuario `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="45fd0-113">This example changes the value of the `Nickname` user setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#7)]  
  
 <span data-ttu-id="45fd0-114">Para que funcione este ejemplo, la aplicación debe tener una configuración de usuario `Nickname`, de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="45fd0-114">For this example to work, your application must have a `Nickname` user setting, of type `String`.</span></span>  
  
 <span data-ttu-id="45fd0-115">La aplicación guarda la configuración del usuario cuando se cierra.</span><span class="sxs-lookup"><span data-stu-id="45fd0-115">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="45fd0-116">Para guardar la configuración inmediatamente, llame al método `My.Settings.Save`.</span><span class="sxs-lookup"><span data-stu-id="45fd0-116">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="45fd0-117">Para obtener más información, vea [Cómo: Conservar la configuración del usuario en Visual Basic](how-to-persist-user-settings.md).</span><span class="sxs-lookup"><span data-stu-id="45fd0-117">For more information, see [How to: Persist User Settings in Visual Basic](how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45fd0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="45fd0-118">See also</span></span>

- [<span data-ttu-id="45fd0-119">My.Settings (objeto)</span><span class="sxs-lookup"><span data-stu-id="45fd0-119">My.Settings Object</span></span>](../../../language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="45fd0-120">Cómo: Leer la configuración de la aplicación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45fd0-120">How to: Read Application Settings in Visual Basic</span></span>](how-to-read-application-settings.md)
- [<span data-ttu-id="45fd0-121">Cómo: Conservar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45fd0-121">How to: Persist User Settings in Visual Basic</span></span>](how-to-persist-user-settings.md)
- [<span data-ttu-id="45fd0-122">Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45fd0-122">How to: Create Property Grids for User Settings in Visual Basic</span></span>](how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="45fd0-123">Administrar la configuración de la aplicación (.NET)</span><span class="sxs-lookup"><span data-stu-id="45fd0-123">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
