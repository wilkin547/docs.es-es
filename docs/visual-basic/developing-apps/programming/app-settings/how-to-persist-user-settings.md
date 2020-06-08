---
title: Procedimiento para conservar la configuración del usuario
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
ms.openlocfilehash: 817111060259bdfbbb26d9f8eafeae439e1f651f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410158"
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a><span data-ttu-id="619db-102">Procedimiento para conservar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="619db-102">How to: Persist User Settings in Visual Basic</span></span>

<span data-ttu-id="619db-103">Puede usar el método `My.Settings.Save` para conservar los cambios en la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="619db-103">You can use the `My.Settings.Save` method to persist changes to the user settings.</span></span>  
  
 <span data-ttu-id="619db-104">Normalmente, las aplicaciones están diseñadas para conservar los cambios en la configuración de usuario cuando se cierra la aplicación.</span><span class="sxs-lookup"><span data-stu-id="619db-104">Typically, applications are designed to persist the changes to the user settings when the application shuts down.</span></span> <span data-ttu-id="619db-105">La causa de esto es que guardar la configuración puede tardar varios segundos, en función de varios factores.</span><span class="sxs-lookup"><span data-stu-id="619db-105">This is because saving the settings can take, depending on several factors, several seconds.</span></span>  
  
 <span data-ttu-id="619db-106">Para más información, consulte [My.Settings (Objeto)](../../../language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="619db-106">For more information, see [My.Settings Object](../../../language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="619db-107">Aunque puede cambiar y guardar los valores de configuración con ámbito de usuario en tiempo de ejecución, la configuración con ámbito de aplicación es de solo lectura y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="619db-107">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="619db-108">Puede cambiar la configuración con ámbito de aplicación al crear la aplicación mediante el **Diseñador de proyectos** o editando el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="619db-108">You can change application-scope settings when creating the application, through the **Project Designer**, or by editing the application's configuration file.</span></span> <span data-ttu-id="619db-109">Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="619db-109">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="619db-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="619db-110">Example</span></span>  

 <span data-ttu-id="619db-111">Este ejemplo cambia el valor de la configuración de usuario `LastChanged` y guarda el cambio llamando al método `My.Settings.Save`.</span><span class="sxs-lookup"><span data-stu-id="619db-111">This example changes the value of the `LastChanged` user setting and saves that change by calling the `My.Settings.Save` method.</span></span>  
  
 [!code-vb[VbVbalrMyResources#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#5)]  
  
 <span data-ttu-id="619db-112">Para que este ejemplo funcione, la aplicación debe tener una configuración de usuario `LastChanged`, de tipo `Date`.</span><span class="sxs-lookup"><span data-stu-id="619db-112">For this example to work, your application must have a `LastChanged` user setting, of type `Date`.</span></span> <span data-ttu-id="619db-113">Para obtener más información, consulte [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="619db-113">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="619db-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="619db-114">See also</span></span>

- [<span data-ttu-id="619db-115">My.Settings (objeto)</span><span class="sxs-lookup"><span data-stu-id="619db-115">My.Settings Object</span></span>](../../../language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="619db-116">Cómo: Leer la configuración de la aplicación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="619db-116">How to: Read Application Settings in Visual Basic</span></span>](how-to-read-application-settings.md)
- [<span data-ttu-id="619db-117">Cómo: Cambiar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="619db-117">How to: Change User Settings in Visual Basic</span></span>](how-to-change-user-settings.md)
- [<span data-ttu-id="619db-118">Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="619db-118">How to: Create Property Grids for User Settings in Visual Basic</span></span>](how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="619db-119">Administrar la configuración de la aplicación (.NET)</span><span class="sxs-lookup"><span data-stu-id="619db-119">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
