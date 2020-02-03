---
title: Enlazar el control a un tipo mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 2257489e123ceeea819ad3538952db51b726c7e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742018"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="88aac-102">Cómo: Enlazar un control de formularios Windows Forms a un tipo mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="88aac-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>

<span data-ttu-id="88aac-103">Al crear controles que interactúan con datos, a veces necesita enlazar un control a un tipo, en lugar de a un objeto.</span><span class="sxs-lookup"><span data-stu-id="88aac-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="88aac-104">Normalmente necesita enlazar un control a un tipo en tiempo de diseño, cuando quizá no estén disponibles los datos, pero aún desea que los controles enlazados a datos muestren datos de una interfaz pública del tipo.</span><span class="sxs-lookup"><span data-stu-id="88aac-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="88aac-105">Los procedimientos siguientes muestran cómo crear un nuevo <xref:System.Windows.Forms.BindingSource> que está enlazado a un tipo y, a continuación, cómo enlazar una de las propiedades del tipo a la propiedad <xref:System.Windows.Forms.TextBox.Text%2A> de una <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="88aac-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>

### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="88aac-106">Para enlazar BindingSource a un tipo</span><span class="sxs-lookup"><span data-stu-id="88aac-106">To bind the BindingSource to a type</span></span>

1. <span data-ttu-id="88aac-107">Cree un proyecto de Windows Forms (**archivo** > **nuevo** **proyecto** >  > **Visual C#**  o **Visual Basic** > **escritorio clásico** > **aplicación**).</span><span class="sxs-lookup"><span data-stu-id="88aac-107">Create a Windows Forms project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="88aac-108">En la vista **diseño** , arrastre un componente <xref:System.Windows.Forms.BindingSource> al formulario.</span><span class="sxs-lookup"><span data-stu-id="88aac-108">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>

3. <span data-ttu-id="88aac-109">En la ventana **propiedades** , haga clic en la flecha de la propiedad <xref:System.Windows.Forms.BindingSource.DataSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="88aac-109">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>

4. <span data-ttu-id="88aac-110">En el **Editor de tipos de la interfaz de usuario de orígenes de datos**, haga clic en **Agregar origen de datos del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="88aac-110">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>

5. <span data-ttu-id="88aac-111">En la página **Elegir un tipo de origen de datos**, seleccione **Objeto** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="88aac-111">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>

6. <span data-ttu-id="88aac-112">Seleccione el tipo al que desea enlazarlo:</span><span class="sxs-lookup"><span data-stu-id="88aac-112">Select the type to bind to:</span></span>

    - <span data-ttu-id="88aac-113">Si el tipo al que desea enlazarlo se encuentra en el proyecto actual o el ensamblado que contiene el tipo ya se ha agregado como una referencia, expanda los nodos para encontrar el tipo que desee y a continuación selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="88aac-113">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>

      <span data-ttu-id="88aac-114">O bien</span><span class="sxs-lookup"><span data-stu-id="88aac-114">\-or-</span></span>

    - <span data-ttu-id="88aac-115">Si el tipo al que desea enlazar está en otro ensamblado, no actualmente en la lista de referencias, haga clic en **Agregar referencia**y, a continuación, haga clic en la pestaña **proyectos** . Seleccione el proyecto que contiene el objeto comercial que desee y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="88aac-115">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="88aac-116">Este proyecto aparecerá en la lista de ensamblados, por lo que puede expandir los nodos para encontrar el tipo desee y, a continuación, seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="88aac-116">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>

      > [!NOTE]
      > <span data-ttu-id="88aac-117">Si desea enlazar a un tipo de un marco o un ensamblado de Microsoft, desactive la casilla **Ocultar los ensamblados que empiecen por Microsoft o sistema**.</span><span class="sxs-lookup"><span data-stu-id="88aac-117">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>

7. <span data-ttu-id="88aac-118">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="88aac-118">Click **Next**, and then click **Finish**.</span></span>

### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="88aac-119">Para enlazar el control a BindingSource</span><span class="sxs-lookup"><span data-stu-id="88aac-119">To bind the control to the BindingSource</span></span>

1. <span data-ttu-id="88aac-120">Agregue un control <xref:System.Windows.Forms.TextBox> al formulario.</span><span class="sxs-lookup"><span data-stu-id="88aac-120">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>

2. <span data-ttu-id="88aac-121">En la ventana **Propiedades**, expanda el nodo **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="88aac-121">In the **Properties** window, expand the **(DataBindings)** node.</span></span>

3. <span data-ttu-id="88aac-122">Haga clic en la flecha situada junto a la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="88aac-122">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

4. <span data-ttu-id="88aac-123">En el **Editor de tipos de interfaz de usuario de DataSource**, expanda el nodo del <xref:System.Windows.Forms.BindingSource> agregado anteriormente y seleccione la propiedad del tipo enlazado que desea enlazar a la propiedad <xref:System.Windows.Forms.TextBox.Text%2A> de la <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="88aac-123">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>

## <a name="see-also"></a><span data-ttu-id="88aac-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88aac-124">See also</span></span>

- [<span data-ttu-id="88aac-125">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="88aac-125">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="88aac-126">Cómo: Enlazar un control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="88aac-126">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
- [<span data-ttu-id="88aac-127">Enlazar controles a los datos en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="88aac-127">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
