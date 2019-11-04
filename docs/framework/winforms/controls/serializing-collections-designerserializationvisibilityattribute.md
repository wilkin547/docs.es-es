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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 297a7080b0c34fa10f976cbbbfb48d8c35786aca
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458081"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a><span data-ttu-id="1ebf8-102">Tutorial: serializar colecciones de tipos estándar</span><span class="sxs-lookup"><span data-stu-id="1ebf8-102">Walkthrough: Serialize collections of standard types</span></span>

<span data-ttu-id="1ebf8-103">A veces, los controles personalizados exponen una colección como una propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="1ebf8-104">En este tutorial se muestra cómo usar la clase <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> para controlar cómo se serializa una colección en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="1ebf8-105">La aplicación del valor <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> a la propiedad de colección garantiza que se serializará la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="1ebf8-106">Para copiar el código de este tema como una sola lista, vea [Cómo: serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="1ebf8-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ebf8-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1ebf8-107">Prerequisites</span></span>

<span data-ttu-id="1ebf8-108">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="1ebf8-109">Crear un control con una colección serializable</span><span class="sxs-lookup"><span data-stu-id="1ebf8-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="1ebf8-110">El primer paso es crear un control que tenga una colección serializable como una propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="1ebf8-111">Puede editar el contenido de esta colección mediante el editor de la **colección**, al que puede tener acceso desde la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="1ebf8-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="1ebf8-112">En Visual Studio, cree un proyecto de biblioteca de controles de Windows y asígnele el nombre **SerializationDemoControlLib**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-112">In Visual Studio, create a Windows Control Library project, and name it **SerializationDemoControlLib**.</span></span>

2. <span data-ttu-id="1ebf8-113">Cambie el nombre de `UserControl1` a `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-113">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="1ebf8-114">Para obtener más información, vea [cambiar el nombre de una refactorización de símbolo de código](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="1ebf8-114">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="1ebf8-115">En la ventana **propiedades** , establezca el valor de la propiedad <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> en **10**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-115">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to **10**.</span></span>

4. <span data-ttu-id="1ebf8-116">Coloque un control <xref:System.Windows.Forms.TextBox> en el `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-116">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="1ebf8-117">Seleccione el control <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-117">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="1ebf8-118">En la ventana **propiedades** , establezca las siguientes propiedades.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-118">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="1ebf8-119">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-119">Property</span></span>|<span data-ttu-id="1ebf8-120">Cambiar a</span><span class="sxs-lookup"><span data-stu-id="1ebf8-120">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="1ebf8-121">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="1ebf8-121">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="1ebf8-122">**Anclaje**</span><span class="sxs-lookup"><span data-stu-id="1ebf8-122">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="1ebf8-123">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="1ebf8-123">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="1ebf8-124">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="1ebf8-124">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="1ebf8-125">En el **Editor de código**, declare un campo de matriz de cadenas denominado `stringsValue` en `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-125">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="1ebf8-126">Defina la propiedad `Strings` en el `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-126">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1ebf8-127">El valor <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> se usa para habilitar la serialización de la colección.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-127">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="1ebf8-128">Presione **F5** para compilar el proyecto y ejecutar el control en **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-128">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="1ebf8-129">Busque la propiedad **Strings** en el <xref:System.Windows.Forms.PropertyGrid> de **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-129">Find the **Strings** property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="1ebf8-130">Seleccione la propiedad **cadenas** y, a continuación, seleccione los puntos suspensivos (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio](./media/visual-studio-ellipsis-button.png)) para abrir el editor de la **colección de cadenas**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-130">Select the **Strings** property, then select the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="1ebf8-131">Escriba varias cadenas en el **Editor de colección de cadenas**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-131">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="1ebf8-132">Sepárelos presionando la tecla **entrar** al final de cada cadena.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-132">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="1ebf8-133">Haga clic en **Aceptar** cuando haya terminado de escribir las cadenas.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-133">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1ebf8-134">Las cadenas que escribió aparecen en el <xref:System.Windows.Forms.TextBox> de la `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-134">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serialize-a-collection-property"></a><span data-ttu-id="1ebf8-135">Serializar una propiedad de colección</span><span class="sxs-lookup"><span data-stu-id="1ebf8-135">Serialize a collection property</span></span>

<span data-ttu-id="1ebf8-136">Para probar el comportamiento de la serialización del control, lo colocará en un formulario y cambiará el contenido de la colección con el editor de la **colección**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-136">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="1ebf8-137">Puede ver el estado de la colección serializada examinando un archivo de diseñador especial en el que el **Diseñador de Windows Forms** emite el código.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-137">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

1. <span data-ttu-id="1ebf8-138">Agregue un proyecto de aplicación para Windows a la solución.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-138">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="1ebf8-139">Dé un nombre al proyecto `SerializationDemoControlTest`.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-139">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="1ebf8-140">En el **cuadro de herramientas**, busque la pestaña denominada **SerializationDemoControlLib Components**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-140">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="1ebf8-141">En esta pestaña, encontrará el `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-141">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="1ebf8-142">Para más información, consulte [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="1ebf8-142">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="1ebf8-143">Coloque un `SerializationDemoControl` en el formulario.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-143">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="1ebf8-144">Busque la propiedad `Strings` en la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="1ebf8-144">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="1ebf8-145">Haga clic en la propiedad `Strings` y, a continuación, haga clic en los puntos suspensivos (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) para abrir el editor de la **colección de cadenas**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-145">Click the `Strings` property, then click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="1ebf8-146">Escriba varias cadenas en el **Editor**de la colección de cadenas.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-146">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="1ebf8-147">Sepárelos presionando **entrar** al final de cada cadena.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-147">Separate them by pressing **Enter** at the end of each string.</span></span> <span data-ttu-id="1ebf8-148">Haga clic en **Aceptar** cuando haya terminado de escribir las cadenas.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-148">Click **OK** when you are finished entering strings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1ebf8-149">Las cadenas que escribió aparecen en el <xref:System.Windows.Forms.TextBox> de la `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-149">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

6. <span data-ttu-id="1ebf8-150">En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-150">In **Solution Explorer**, click the **Show All Files** button.</span></span>

7. <span data-ttu-id="1ebf8-151">Abra el nodo **Form1** .</span><span class="sxs-lookup"><span data-stu-id="1ebf8-151">Open the **Form1** node.</span></span> <span data-ttu-id="1ebf8-152">Debajo, se trata de un archivo denominado **Form1.Designer.CS** o **Form1. Designer. VB**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-152">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="1ebf8-153">Este es el archivo en el que el **Diseñador de Windows Forms** emite código que representa el estado de tiempo de diseño del formulario y sus controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-153">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="1ebf8-154">Abra este archivo en el **Editor de código**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-154">Open this file in the **Code Editor**.</span></span>

8. <span data-ttu-id="1ebf8-155">Abra la región denominada **código generado por el diseñador de Windows Forms** y busque la sección con la etiqueta **serializationDemoControl1**.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-155">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="1ebf8-156">Debajo de esta etiqueta se encuentra el código que representa el estado serializado del control.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-156">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="1ebf8-157">Las cadenas que escribió en el paso 5 aparecen en una asignación a la propiedad `Strings`.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-157">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="1ebf8-158">En los siguientes ejemplos de C# código de y Visual Basic, se muestra código similar al que se verá si se escriben las cadenas "red", "naranja" y "amarillo".</span><span class="sxs-lookup"><span data-stu-id="1ebf8-158">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. <span data-ttu-id="1ebf8-159">En el **Editor de código**, cambie el valor de la <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> en la propiedad `Strings` a <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-159">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. <span data-ttu-id="1ebf8-160">Recompile la solución y repita los pasos 3 y 4.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-160">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="1ebf8-161">En este caso, el **Diseñador de Windows Forms** no emite ninguna asignación a la propiedad `Strings`.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-161">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1ebf8-162">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1ebf8-162">Next steps</span></span>

<span data-ttu-id="1ebf8-163">Una vez que sepa cómo serializar una colección de tipos estándar, considere la posibilidad de integrar los controles personalizados más profundamente en el entorno en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="1ebf8-163">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="1ebf8-164">En los temas siguientes se describe cómo mejorar la integración en tiempo de diseño de los controles personalizados:</span><span class="sxs-lookup"><span data-stu-id="1ebf8-164">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="1ebf8-165">[Arquitectura en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="1ebf8-165">[Design-Time Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="1ebf8-166">Atributos en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1ebf8-166">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="1ebf8-167">[Información general sobre la serialización del diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="1ebf8-167">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="1ebf8-168">Tutorial: Crear un control de Windows Forms que aproveche las características en tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1ebf8-168">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="1ebf8-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ebf8-169">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [<span data-ttu-id="1ebf8-170">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="1ebf8-170">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
