---
title: Procedimiento para enlazar un control de formularios Windows Forms a un tipo mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: daddbee9aa5eff55bf12a5d8c53ad59001a0c308
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64612444"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="2f416-102">Procedimiento para enlazar un control de formularios Windows Forms a un tipo mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="2f416-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>
<span data-ttu-id="2f416-103">Al crear controles que interactúan con datos, a veces necesita enlazar un control a un tipo, en lugar de a un objeto.</span><span class="sxs-lookup"><span data-stu-id="2f416-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="2f416-104">Normalmente necesita enlazar un control a un tipo en tiempo de diseño, cuando quizá no estén disponibles los datos, pero aún desea que los controles enlazados a datos muestren datos de una interfaz pública del tipo.</span><span class="sxs-lookup"><span data-stu-id="2f416-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="2f416-105">Los procedimientos siguientes muestran cómo crear un nuevo <xref:System.Windows.Forms.BindingSource> decir enlazado a un tipo y, a continuación, cómo enlazar una de las propiedades del tipo para el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad de un <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2f416-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="2f416-106">Para enlazar BindingSource a un tipo</span><span class="sxs-lookup"><span data-stu-id="2f416-106">To bind the BindingSource to a type</span></span>  
  
1. <span data-ttu-id="2f416-107">Crear un proyecto de Windows Forms (**archivo** > **New** > **proyecto** > **Visual C#** o **Visual Basic** > **escritorio clásico de** > **aplicación de Windows Forms**).</span><span class="sxs-lookup"><span data-stu-id="2f416-107">Create a Windows Forms project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="2f416-108">En **diseño** ver, arrastre un <xref:System.Windows.Forms.BindingSource> componente al formulario.</span><span class="sxs-lookup"><span data-stu-id="2f416-108">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>  
  
3. <span data-ttu-id="2f416-109">En el **propiedades** ventana, haga clic en la flecha de la <xref:System.Windows.Forms.BindingSource.DataSource%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2f416-109">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>  
  
4. <span data-ttu-id="2f416-110">En el **Editor de tipos de la interfaz de usuario de orígenes de datos**, haga clic en **Agregar origen de datos del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="2f416-110">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>  
  
5. <span data-ttu-id="2f416-111">En la página **Elegir un tipo de origen de datos**, seleccione **Objeto** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2f416-111">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>  
  
6. <span data-ttu-id="2f416-112">Seleccione el tipo al que desea enlazarlo:</span><span class="sxs-lookup"><span data-stu-id="2f416-112">Select the type to bind to:</span></span>  
  
    - <span data-ttu-id="2f416-113">Si el tipo al que desea enlazarlo se encuentra en el proyecto actual o el ensamblado que contiene el tipo ya se ha agregado como una referencia, expanda los nodos para encontrar el tipo que desee y a continuación selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="2f416-113">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>  
  
         <span data-ttu-id="2f416-114">-o bien-</span><span class="sxs-lookup"><span data-stu-id="2f416-114">-or-</span></span>  
  
    - <span data-ttu-id="2f416-115">Si el tipo al que desea enlazarlo se encuentra en otro ensamblado, no actualmente en la lista de referencias, haga clic en **Agregar referencia** y después haga clic en la pestaña **Proyectos**. Seleccione el proyecto que contiene el objeto comercial que desea y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2f416-115">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="2f416-116">Este proyecto aparecerá en la lista de ensamblados, por lo que puede expandir los nodos para encontrar el tipo desee y, a continuación, seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="2f416-116">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="2f416-117">Si desea enlazar a un tipo de un marco o un ensamblado de Microsoft, desactive la casilla **Ocultar los ensamblados que empiecen por Microsoft o sistema**.</span><span class="sxs-lookup"><span data-stu-id="2f416-117">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>  
  
7. <span data-ttu-id="2f416-118">Haga clic en **Siguiente** y después haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2f416-118">Click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="2f416-119">Para enlazar el control a BindingSource</span><span class="sxs-lookup"><span data-stu-id="2f416-119">To bind the control to the BindingSource</span></span>  
  
1. <span data-ttu-id="2f416-120">Agregue un control <xref:System.Windows.Forms.TextBox> al formulario.</span><span class="sxs-lookup"><span data-stu-id="2f416-120">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>  
  
2. <span data-ttu-id="2f416-121">En la ventana **Propiedades**, expanda el nodo **(DataBindings)**.</span><span class="sxs-lookup"><span data-stu-id="2f416-121">In the **Properties** window, expand the **(DataBindings)** node.</span></span>  
  
3. <span data-ttu-id="2f416-122">Haga clic en la flecha situada junto a la <xref:System.Windows.Forms.TextBox.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2f416-122">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
4. <span data-ttu-id="2f416-123">En el **Editor de tipos de interfaz de usuario de origen de datos**, expanda el nodo de la <xref:System.Windows.Forms.BindingSource> agregado previamente y seleccione la propiedad del tipo enlazado que desea enlazar el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad de la <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2f416-123">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f416-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f416-124">See also</span></span>

- [<span data-ttu-id="2f416-125">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="2f416-125">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="2f416-126">Cómo: Enlazar un Control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="2f416-126">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
- [<span data-ttu-id="2f416-127">Enlazar controles a los datos en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2f416-127">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
