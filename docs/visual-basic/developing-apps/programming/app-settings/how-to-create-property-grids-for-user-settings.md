---
description: 'Más información acerca de: Procedimiento: para crear cuadrículas de propiedades para la configuración del usuario en Visual Basic'
title: Procedimiento para crear cuadrículas de propiedades para la configuración del usuario
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], creating property grids for user settings
- user settings [Visual Basic], creating property grids
- property grids [Visual Basic], creating for user settings
- property grids
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
ms.openlocfilehash: 19523f712207cac225ccf68e02e338a9e76fe358
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797853"
---
# <a name="how-to-create-property-grids-for-user-settings-in-visual-basic"></a><span data-ttu-id="4409b-103">Cómo: Crear cuadrículas de propiedades para la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4409b-103">How to: Create Property Grids for User Settings in Visual Basic</span></span>

<span data-ttu-id="4409b-104">Una cuadrícula de propiedades para la configuración del usuario se crea rellenando un control <xref:System.Windows.Forms.PropertyGrid> con las propiedades de configuración de usuario del objeto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="4409b-104">You can create a property grid for user settings by populating a <xref:System.Windows.Forms.PropertyGrid> control with the user setting properties of the `My.Settings` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4409b-105">Para que funcione este ejemplo, la aplicación debe tener configurados los ajustes del usuario.</span><span class="sxs-lookup"><span data-stu-id="4409b-105">In order for this example to work, your application must have its user settings configured.</span></span> <span data-ttu-id="4409b-106">Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="4409b-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
 <span data-ttu-id="4409b-107">El objeto `My.Settings` expone cada configuración como una propiedad.</span><span class="sxs-lookup"><span data-stu-id="4409b-107">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="4409b-108">El nombre de propiedad es el mismo que el nombre de la configuración y el tipo de propiedad es el mismo que el tipo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4409b-108">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="4409b-109">El **Ámbito** de la configuración determina si la propiedad es de solo lectura. La propiedad de una configuración con ámbito **Aplicación** es de solo lectura, mientras que la propiedad de una configuración con ámbito **Usuario** es de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="4409b-109">The setting's **Scope** determines if the property is read-only; the property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="4409b-110">Para obtener más información, vea [My.Settings (Objeto)](../../../language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="4409b-110">For more information, see [My.Settings Object](../../../language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4409b-111">No se pueden cambiar ni guardar los valores de configuración de ámbito de aplicación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4409b-111">You cannot change or save the values of application-scope settings at run time.</span></span> <span data-ttu-id="4409b-112">Las configuraciones con ámbito de aplicación únicamente se pueden cambiar al crear la aplicación (mediante el **Diseñador de proyectos**) o editando el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4409b-112">Application-scope settings can be changed only when creating the application (through the **Project Designer**) or by editing the application's configuration file.</span></span> <span data-ttu-id="4409b-113">Para obtener más información, vea [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="4409b-113">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
 <span data-ttu-id="4409b-114">Este ejemplo usa un control <xref:System.Windows.Forms.PropertyGrid> para acceder a las propiedades de configuración de usuario del objeto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="4409b-114">This example uses a <xref:System.Windows.Forms.PropertyGrid> control to access the user-setting properties of the `My.Settings` object.</span></span> <span data-ttu-id="4409b-115">De forma predeterminada, <xref:System.Windows.Forms.PropertyGrid> muestra todas las propiedades del objeto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="4409b-115">By default, the <xref:System.Windows.Forms.PropertyGrid> shows all the properties of the `My.Settings` object.</span></span> <span data-ttu-id="4409b-116">Sin embargo, las propiedades de configuración de usuario tienen el atributo <xref:System.Configuration.UserScopedSettingAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4409b-116">However, the user-setting properties have the <xref:System.Configuration.UserScopedSettingAttribute> attribute.</span></span> <span data-ttu-id="4409b-117">Este ejemplo establece la propiedad <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> de <xref:System.Windows.Forms.PropertyGrid> en <xref:System.Configuration.UserScopedSettingAttribute> para mostrar solo las propiedades de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="4409b-117">This example sets the <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> property of the <xref:System.Windows.Forms.PropertyGrid> to <xref:System.Configuration.UserScopedSettingAttribute> to display only the user-setting properties.</span></span>  
  
### <a name="to-add-a-user-setting-property-grid"></a><span data-ttu-id="4409b-118">Para agregar una cuadrícula de propiedades de configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="4409b-118">To add a user setting property grid</span></span>  
  
1. <span data-ttu-id="4409b-119">Agregue el control **PropertyGrid** desde el **Cuadro de herramientas** a la superficie de diseño de la aplicación, que aquí se da por supuesto que es `Form1`.</span><span class="sxs-lookup"><span data-stu-id="4409b-119">Add the **PropertyGrid** control from the **Toolbox** to the design surface for your application, assumed here to be `Form1`.</span></span>  
  
     <span data-ttu-id="4409b-120">El nombre predeterminado del control de cuadrícula de propiedades es `PropertyGrid1`.</span><span class="sxs-lookup"><span data-stu-id="4409b-120">The default name of the property-grid control is `PropertyGrid1`.</span></span>  
  
2. <span data-ttu-id="4409b-121">Haga doble clic en la superficie de diseño de `Form1` para abrir el código del controlador de eventos de carga del formulario.</span><span class="sxs-lookup"><span data-stu-id="4409b-121">Double-click the design surface for `Form1` to open the code for the form-load event handler.</span></span>  
  
3. <span data-ttu-id="4409b-122">Establezca el objeto `My.Settings` como el objeto seleccionado para la cuadrícula de propiedades.</span><span class="sxs-lookup"><span data-stu-id="4409b-122">Set the `My.Settings` object as the selected object for the property grid.</span></span>  
  
     [!code-vb[VbVbalrMyResources#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#11)]  
  
4. <span data-ttu-id="4409b-123">Configure la cuadrícula de propiedades para que solo muestre la configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="4409b-123">Configure the property grid to show only the user settings.</span></span>  
  
     [!code-vb[VbVbalrMyResources#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#12)]  
  
    > [!NOTE]
    > <span data-ttu-id="4409b-124">Para mostrar solo la configuración del ámbito de aplicación, utilice el atributo <xref:System.Configuration.ApplicationScopedSettingAttribute> en lugar de <xref:System.Configuration.UserScopedSettingAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4409b-124">To show only the application-scope settings, use the <xref:System.Configuration.ApplicationScopedSettingAttribute> attribute instead of  <xref:System.Configuration.UserScopedSettingAttribute>.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4409b-125">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="4409b-125">Robust Programming</span></span>  

 <span data-ttu-id="4409b-126">La aplicación guarda la configuración del usuario cuando se cierra.</span><span class="sxs-lookup"><span data-stu-id="4409b-126">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="4409b-127">Para guardar la configuración inmediatamente, llame al método `My.Settings.Save`.</span><span class="sxs-lookup"><span data-stu-id="4409b-127">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="4409b-128">Para obtener más información, vea [Cómo: Conservar la configuración del usuario en Visual Basic](how-to-persist-user-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4409b-128">For more information, see [How to: Persist User Settings in Visual Basic](how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4409b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4409b-129">See also</span></span>

- [<span data-ttu-id="4409b-130">My.Settings (objeto)</span><span class="sxs-lookup"><span data-stu-id="4409b-130">My.Settings Object</span></span>](../../../language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="4409b-131">Cómo: Leer la configuración de la aplicación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4409b-131">How to: Read Application Settings in Visual Basic</span></span>](how-to-read-application-settings.md)
- [<span data-ttu-id="4409b-132">Cómo: Cambiar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4409b-132">How to: Change User Settings in Visual Basic</span></span>](how-to-change-user-settings.md)
- [<span data-ttu-id="4409b-133">Cómo: Conservar la configuración del usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4409b-133">How to: Persist User Settings in Visual Basic</span></span>](how-to-persist-user-settings.md)
- [<span data-ttu-id="4409b-134">Administrar la configuración de la aplicación (.NET)</span><span class="sxs-lookup"><span data-stu-id="4409b-134">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
