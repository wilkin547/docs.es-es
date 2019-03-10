---
title: 'Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: b5b5295e61f2a417c3565e62000021019381536f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712193"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="a7569-102">Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="a7569-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>
<span data-ttu-id="a7569-103">A veces, los controles personalizados expondrá una colección como una propiedad.</span><span class="sxs-lookup"><span data-stu-id="a7569-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="a7569-104">Este tutorial muestra cómo usar el <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> clase para controlar cómo se serializa una colección en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="a7569-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="a7569-105">Aplicar el <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valor a la propiedad de colección se asegura de que se va a serializar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a7569-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>  
  
 <span data-ttu-id="a7569-106">Para copiar el código de este tema como una sola lista, vea [Cómo: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="a7569-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7569-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="a7569-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a7569-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="a7569-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a7569-109">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="a7569-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a7569-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a7569-110">Prerequisites</span></span>  
 <span data-ttu-id="a7569-111">Para poder completar este tutorial, necesitará:</span><span class="sxs-lookup"><span data-stu-id="a7569-111">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="a7569-112">Permisos suficientes para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde está instalado Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a7569-112">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a><span data-ttu-id="a7569-113">Crear un Control que tiene una colección Serializable</span><span class="sxs-lookup"><span data-stu-id="a7569-113">Creating a Control That Has a Serializable Collection</span></span>  
 <span data-ttu-id="a7569-114">El primer paso es crear un control que tiene una colección serializable como una propiedad.</span><span class="sxs-lookup"><span data-stu-id="a7569-114">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="a7569-115">Puede editar el contenido de esta colección con el **Editor de la colección**, que se puede acceder desde el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="a7569-115">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a><span data-ttu-id="a7569-116">Para crear un control con una colección serializable</span><span class="sxs-lookup"><span data-stu-id="a7569-116">To create a control with a serializable collection</span></span>  
  
1.  <span data-ttu-id="a7569-117">Cree un proyecto de biblioteca de controles de Windows denominado `SerializationDemoControlLib`.</span><span class="sxs-lookup"><span data-stu-id="a7569-117">Create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="a7569-118">Para obtener más información, consulte [plantilla Biblioteca de controles de Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a7569-118">For more information, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="a7569-119">Cambiar el nombre de `UserControl1` a `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="a7569-119">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="a7569-120">Para obtener más información, consulte [cambiar el nombre de una refactorización de código símbolos](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="a7569-120">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>  
  
3.  <span data-ttu-id="a7569-121">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> propiedad `10`.</span><span class="sxs-lookup"><span data-stu-id="a7569-121">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>  
  
4.  <span data-ttu-id="a7569-122">Colocar un <xref:System.Windows.Forms.TextBox> en controlar la `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="a7569-122">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>  
  
5.  <span data-ttu-id="a7569-123">Seleccione el control <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="a7569-123">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="a7569-124">En el **propiedades** ventana, establezca las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="a7569-124">In the **Properties** window, set the following properties.</span></span>  
  
    |<span data-ttu-id="a7569-125">Property</span><span class="sxs-lookup"><span data-stu-id="a7569-125">Property</span></span>|<span data-ttu-id="a7569-126">Cambiar a</span><span class="sxs-lookup"><span data-stu-id="a7569-126">Change to</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="a7569-127">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="a7569-127">**Multiline**</span></span>|`true`|  
    |<span data-ttu-id="a7569-128">**Acoplar**</span><span class="sxs-lookup"><span data-stu-id="a7569-128">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |<span data-ttu-id="a7569-129">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="a7569-129">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |<span data-ttu-id="a7569-130">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="a7569-130">**ReadOnly**</span></span>|`true`|  
  
6.  <span data-ttu-id="a7569-131">En el **Editor de código**, declare un campo de matriz de cadena denominado `stringsValue` en `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="a7569-131">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  <span data-ttu-id="a7569-132">Definir la `Strings` propiedad en el `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="a7569-132">Define the `Strings` property on the `SerializationDemoControl`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7569-133">El <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valor se utiliza para habilitar la serialización de la colección.</span><span class="sxs-lookup"><span data-stu-id="a7569-133">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  <span data-ttu-id="a7569-134">Presione F5 para compilar el proyecto y ejecutar el control en **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="a7569-134">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="a7569-135">Buscar el `Strings` propiedad en el <xref:System.Windows.Forms.PropertyGrid> de la **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="a7569-135">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="a7569-136">Haga clic en el `Strings` propiedad, a continuación, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) para abrir el **deEditordecoleccióndecadenas**.</span><span class="sxs-lookup"><span data-stu-id="a7569-136">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="a7569-137">Escriba varias cadenas en el **Editor de colección de cadenas**.</span><span class="sxs-lookup"><span data-stu-id="a7569-137">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="a7569-138">Deberá separarlos presionando la tecla ENTRAR al final de cada cadena.</span><span class="sxs-lookup"><span data-stu-id="a7569-138">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="a7569-139">Haga clic en **Aceptar** cuando haya terminado de escribir cadenas.</span><span class="sxs-lookup"><span data-stu-id="a7569-139">Click **OK** when you are finished entering strings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7569-140">Aparecen las cadenas que escribió en el <xref:System.Windows.Forms.TextBox> de la `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="a7569-140">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>  
  
## <a name="serializing-a-collection-property"></a><span data-ttu-id="a7569-141">Serializar una propiedad de colección</span><span class="sxs-lookup"><span data-stu-id="a7569-141">Serializing a Collection Property</span></span>  
 <span data-ttu-id="a7569-142">Para probar el comportamiento de serialización del control, que lo coloca en un formulario y cambiar el contenido de la colección con el **Editor de la colección**.</span><span class="sxs-lookup"><span data-stu-id="a7569-142">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="a7569-143">Puede ver el estado de la colección serializada si examina un archivo de diseñador especial, en la que el **Diseñador de Windows Forms** emite el código.</span><span class="sxs-lookup"><span data-stu-id="a7569-143">You can see the serialized collection state by looking at a special designer file, into which the **Windows Forms Designer** emits code.</span></span>  
  
#### <a name="to-serialize-a-collection"></a><span data-ttu-id="a7569-144">Para serializar una colección</span><span class="sxs-lookup"><span data-stu-id="a7569-144">To serialize a collection</span></span>  
  
1.  <span data-ttu-id="a7569-145">Agregar un proyecto de aplicación de Windows a la solución.</span><span class="sxs-lookup"><span data-stu-id="a7569-145">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="a7569-146">Dé un nombre al proyecto `SerializationDemoControlTest`.</span><span class="sxs-lookup"><span data-stu-id="a7569-146">Name the project `SerializationDemoControlTest`.</span></span>  
  
2.  <span data-ttu-id="a7569-147">En el **cuadro de herramientas**, busque la pestaña denominada **componentes SerializationDemoControlLib**.</span><span class="sxs-lookup"><span data-stu-id="a7569-147">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="a7569-148">En esta pestaña, puede encontrar el `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="a7569-148">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="a7569-149">Para obtener más información, vea [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="a7569-149">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
3.  <span data-ttu-id="a7569-150">Colocar un `SerializationDemoControl` en el formulario.</span><span class="sxs-lookup"><span data-stu-id="a7569-150">Place a `SerializationDemoControl` on your form.</span></span>  
  
4.  <span data-ttu-id="a7569-151">Buscar el `Strings` propiedad en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="a7569-151">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="a7569-152">Haga clic en el `Strings` propiedad, a continuación, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) para abrir el **deEditordecoleccióndecadenas**.</span><span class="sxs-lookup"><span data-stu-id="a7569-152">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>  
  
5.  <span data-ttu-id="a7569-153">Escriba varias cadenas en el **Editor de colección de cadenas**.</span><span class="sxs-lookup"><span data-stu-id="a7569-153">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="a7569-154">Deberá separarlos presionando la tecla ENTRAR al final de cada cadena.</span><span class="sxs-lookup"><span data-stu-id="a7569-154">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="a7569-155">Haga clic en **Aceptar** cuando haya terminado de escribir cadenas.</span><span class="sxs-lookup"><span data-stu-id="a7569-155">Click **OK** when you are finished entering strings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7569-156">Aparecen las cadenas que escribió en el <xref:System.Windows.Forms.TextBox> de la `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="a7569-156">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>  
  
1.  <span data-ttu-id="a7569-157">En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="a7569-157">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
2.  <span data-ttu-id="a7569-158">Abra el **Form1** nodo.</span><span class="sxs-lookup"><span data-stu-id="a7569-158">Open the **Form1** node.</span></span> <span data-ttu-id="a7569-159">Debajo es un archivo denominado **Form1.Designer.cs** o **Form1.Designer.vb**.</span><span class="sxs-lookup"><span data-stu-id="a7569-159">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="a7569-160">Este es el archivo en el que el **Diseñador de Windows Forms** emite código que representa el estado de tiempo de diseño del formulario y sus controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="a7569-160">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="a7569-161">Abra este archivo en el **Editor de código**.</span><span class="sxs-lookup"><span data-stu-id="a7569-161">Open this file in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="a7569-162">Abra la región denominada **código generado por el Diseñador de formularios de Windows** y busque la sección con la etiqueta **serializationDemoControl1**.</span><span class="sxs-lookup"><span data-stu-id="a7569-162">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="a7569-163">Por debajo de esta etiqueta es el código que representa el estado serializado del control.</span><span class="sxs-lookup"><span data-stu-id="a7569-163">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="a7569-164">Las cadenas que escribió en el paso 5 aparecerán en una asignación a la `Strings` propiedad.</span><span class="sxs-lookup"><span data-stu-id="a7569-164">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="a7569-165">Los siguientes ejemplos de código en C# y Visual Basic, se muestra código similar a lo que verá si ha escrito las cadenas "rojo", "orange" y "amarillo".</span><span class="sxs-lookup"><span data-stu-id="a7569-165">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  <span data-ttu-id="a7569-166">En el **Editor de código**, cambie el valor de la <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> en el `Strings` propiedad <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span><span class="sxs-lookup"><span data-stu-id="a7569-166">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. <span data-ttu-id="a7569-167">Vuelva a generar la solución y repita los pasos 3 y 4.</span><span class="sxs-lookup"><span data-stu-id="a7569-167">Rebuild the solution and repeat steps 3 and 4.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7569-168">En este caso, el **Diseñador de Windows Forms** no emite ninguna asignación a la `Strings` propiedad.</span><span class="sxs-lookup"><span data-stu-id="a7569-168">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a7569-169">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a7569-169">Next Steps</span></span>  
 <span data-ttu-id="a7569-170">Una vez que sepa cómo serializar una colección de tipos estándares, considere la posibilidad de integrar los controles personalizados más profundamente en el entorno de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="a7569-170">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="a7569-171">Los temas siguientes describen cómo mejorar la integración de tiempo de diseño de los controles personalizados:</span><span class="sxs-lookup"><span data-stu-id="a7569-171">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>  
  
-   <span data-ttu-id="a7569-172">[Arquitectura en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a7569-172">[Design-Time Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>  
  
-   [<span data-ttu-id="a7569-173">Atributos en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a7569-173">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
  
-   <span data-ttu-id="a7569-174">[Información general de la serialización de diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a7569-174">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>  
  
-   [<span data-ttu-id="a7569-175">Tutorial: Crear un Control de Windows Forms que aproveche las características de tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a7569-175">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a><span data-ttu-id="a7569-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7569-176">See also</span></span>
- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- <span data-ttu-id="a7569-177">[Información general de la serialización de diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a7569-177">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>
- <span data-ttu-id="a7569-178">[Cómo: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a7569-178">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
- [<span data-ttu-id="a7569-179">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="a7569-179">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
