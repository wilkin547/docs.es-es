---
title: Desarrollo de un control simple
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: 5383cee5358dbd260fc6c023d3db607da6b10ea4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742257"
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a><span data-ttu-id="1c621-102">Cómo: Desarrollar un control de formularios Windows Forms sencillo</span><span class="sxs-lookup"><span data-stu-id="1c621-102">How to: Develop a Simple Windows Forms Control</span></span>

<span data-ttu-id="1c621-103">Esta sección le guiará a través de los pasos clave para crear un control de Windows Forms personalizado.</span><span class="sxs-lookup"><span data-stu-id="1c621-103">This section walks you through the key steps for authoring a custom Windows Forms control.</span></span> <span data-ttu-id="1c621-104">El control simple desarrollado en este tutorial permite cambiar la alineación de su <xref:System.Windows.Forms.Control.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c621-104">The simple control developed in this walkthrough allows the alignment of its <xref:System.Windows.Forms.Control.Text%2A> property to be changed.</span></span> <span data-ttu-id="1c621-105">No genera ni controla eventos.</span><span class="sxs-lookup"><span data-stu-id="1c621-105">It does not raise or handle events.</span></span>

### <a name="to-create-a-simple-custom-control"></a><span data-ttu-id="1c621-106">Para crear un control personalizado simple</span><span class="sxs-lookup"><span data-stu-id="1c621-106">To create a simple custom control</span></span>

1. <span data-ttu-id="1c621-107">Defina una clase que se derive de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c621-107">Define a class that derives from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>

    ```vb
    Public Class FirstControl
       Inherits Control

    End Class
    ```

    ```csharp
    public class FirstControl:Control {}
    ```

2. <span data-ttu-id="1c621-108">Defina las propiedades.</span><span class="sxs-lookup"><span data-stu-id="1c621-108">Define properties.</span></span> <span data-ttu-id="1c621-109">(No es necesario definir propiedades, porque un control hereda muchas propiedades de la clase <xref:System.Windows.Forms.Control>, pero la mayoría de los controles personalizados suelen definir propiedades adicionales). En el fragmento de código siguiente se define una propiedad denominada `TextAlignment` que `FirstControl` utiliza para dar formato a la presentación de la propiedad <xref:System.Windows.Forms.Control.Text%2A> heredada de <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="1c621-109">(You are not required to define properties, because a control inherits many properties from the <xref:System.Windows.Forms.Control> class, but most custom controls generally do define additional properties.) The following code fragment defines a property named `TextAlignment` that `FirstControl` uses to format the display of the <xref:System.Windows.Forms.Control.Text%2A> property inherited from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="1c621-110">Para información sobre la definición de propiedades, vea [Introducción a las propiedades](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120)).</span><span class="sxs-lookup"><span data-stu-id="1c621-110">For more information about defining properties, see [Properties Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120)).</span></span>

     [!code-csharp[System.Windows.Forms.FirstControl#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]

     <span data-ttu-id="1c621-111">Al establecer una propiedad que cambia la presentación visual del control, debe invocar el método <xref:System.Windows.Forms.Control.Invalidate%2A> para volver a dibujar el control.</span><span class="sxs-lookup"><span data-stu-id="1c621-111">When you set a property that changes the visual display of the control, you must invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method to redraw the control.</span></span> <span data-ttu-id="1c621-112"><xref:System.Windows.Forms.Control.Invalidate%2A> se define en la <xref:System.Windows.Forms.Control>de la clase base.</span><span class="sxs-lookup"><span data-stu-id="1c621-112"><xref:System.Windows.Forms.Control.Invalidate%2A> is defined in the base class <xref:System.Windows.Forms.Control>.</span></span>

3. <span data-ttu-id="1c621-113">Invalide el método <xref:System.Windows.Forms.Control.OnPaint%2A> protegido heredado de <xref:System.Windows.Forms.Control> para proporcionar lógica de representación al control.</span><span class="sxs-lookup"><span data-stu-id="1c621-113">Override the protected <xref:System.Windows.Forms.Control.OnPaint%2A> method inherited from <xref:System.Windows.Forms.Control> to provide rendering logic to your control.</span></span> <span data-ttu-id="1c621-114">Si no invalida <xref:System.Windows.Forms.Control.OnPaint%2A>, el control no podrá dibujarse a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="1c621-114">If you do not override <xref:System.Windows.Forms.Control.OnPaint%2A>, your control will not be able to draw itself.</span></span> <span data-ttu-id="1c621-115">En el fragmento de código siguiente, el método <xref:System.Windows.Forms.Control.OnPaint%2A> muestra la propiedad <xref:System.Windows.Forms.Control.Text%2A> heredada de <xref:System.Windows.Forms.Control> con la alineación especificada por el campo `alignmentValue`.</span><span class="sxs-lookup"><span data-stu-id="1c621-115">In the following code fragment, the <xref:System.Windows.Forms.Control.OnPaint%2A> method displays the <xref:System.Windows.Forms.Control.Text%2A> property inherited from <xref:System.Windows.Forms.Control> with the alignment specified by the `alignmentValue` field.</span></span>

     [!code-csharp[System.Windows.Forms.FirstControl#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]

4. <span data-ttu-id="1c621-116">Proporcione atributos para el control.</span><span class="sxs-lookup"><span data-stu-id="1c621-116">Provide attributes for your control.</span></span> <span data-ttu-id="1c621-117">Los atributos permiten que un diseñador visual muestre el control y sus propiedades y eventos de forma adecuada en el momento del diseño.</span><span class="sxs-lookup"><span data-stu-id="1c621-117">Attributes enable a visual designer to display your control and its properties and events appropriately at design time.</span></span> <span data-ttu-id="1c621-118">El siguiente fragmento aplica los atributos a la propiedad `TextAlignment`.</span><span class="sxs-lookup"><span data-stu-id="1c621-118">The following code fragment applies attributes to the `TextAlignment` property.</span></span> <span data-ttu-id="1c621-119">En un diseñador como Visual Studio, el <xref:System.ComponentModel.CategoryAttribute.Category%2A> atributo (que se muestra en el fragmento de código) hace que la propiedad se muestre en una categoría lógica.</span><span class="sxs-lookup"><span data-stu-id="1c621-119">In a designer such as Visual Studio, the <xref:System.ComponentModel.CategoryAttribute.Category%2A> attribute (shown in the code fragment) causes the property to be displayed under a logical category.</span></span> <span data-ttu-id="1c621-120">El atributo <xref:System.ComponentModel.DescriptionAttribute.Description%2A> hace que se muestre una cadena descriptiva en la parte inferior de la ventana **propiedades** cuando se selecciona la propiedad `TextAlignment`.</span><span class="sxs-lookup"><span data-stu-id="1c621-120">The <xref:System.ComponentModel.DescriptionAttribute.Description%2A> attribute causes a descriptive string to be displayed at the bottom of the **Properties** window when the `TextAlignment` property is selected.</span></span> <span data-ttu-id="1c621-121">Para información sobre los atributos, vea [Atributos en tiempo de diseño para componentes](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="1c621-121">For more information about attributes, see [Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span></span>

     [!code-csharp[System.Windows.Forms.FirstControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]

5. <span data-ttu-id="1c621-122">(opcional) Proporcione recursos para el control.</span><span class="sxs-lookup"><span data-stu-id="1c621-122">(optional) Provide resources for your control.</span></span> <span data-ttu-id="1c621-123">Puede proporcionar un recurso, como un mapa de bits, para el control mediante una opción de compilador (`/res` para C#) para empaquetar recursos con el control.</span><span class="sxs-lookup"><span data-stu-id="1c621-123">You can provide a resource, such as a bitmap, for your control by using a compiler option (`/res` for C#) to package resources with your control.</span></span> <span data-ttu-id="1c621-124">En tiempo de ejecución, el recurso se puede recuperar utilizando los métodos de la clase <xref:System.Resources.ResourceManager>.</span><span class="sxs-lookup"><span data-stu-id="1c621-124">At run time, the resource can be retrieved using the methods of the <xref:System.Resources.ResourceManager> class.</span></span> <span data-ttu-id="1c621-125">Para más información sobre la creación y uso de recursos, vea [Recursos de aplicaciones de escritorio](../../resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="1c621-125">For more information about creating and using resources, see the [Resources in Desktop Apps](../../resources/index.md).</span></span>

6. <span data-ttu-id="1c621-126">Compile e implemente el control.</span><span class="sxs-lookup"><span data-stu-id="1c621-126">Compile and deploy your control.</span></span> <span data-ttu-id="1c621-127">Para compilar e implementar `FirstControl,`, realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="1c621-127">To compile and deploy `FirstControl,` execute the following steps:</span></span>

    1. <span data-ttu-id="1c621-128">Guarde el código del siguiente ejemplo en un archivo de origen (como FirstControl.cs o FirstControl.vb).</span><span class="sxs-lookup"><span data-stu-id="1c621-128">Save the code in the following sample to a source file (such as FirstControl.cs or FirstControl.vb).</span></span>

    2. <span data-ttu-id="1c621-129">Compile el código fuente en un ensamblado y guárdelo en el directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1c621-129">Compile the source code into an assembly and save it in your application's directory.</span></span> <span data-ttu-id="1c621-130">Para hacer esto, ejecute el siguiente comando desde el directorio que contiene el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="1c621-130">To accomplish this, execute the following command from the directory that contains the source file.</span></span>

        ```console
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb
        ```

        ```console
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs
        ```

         <span data-ttu-id="1c621-131">La opción del compilador `/t:library` indica al compilador que el ensamblado que se va a crear es una biblioteca (y no un archivo ejecutable).</span><span class="sxs-lookup"><span data-stu-id="1c621-131">The `/t:library` compiler option tells the compiler that the assembly you are creating is a library (and not an executable).</span></span> <span data-ttu-id="1c621-132">La opción `/out` especifica la ruta de acceso y el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1c621-132">The `/out` option specifies the path and name of the assembly.</span></span> <span data-ttu-id="1c621-133">La opción `/r` proporciona el nombre de los ensamblados a los que se hace referencia mediante el código.</span><span class="sxs-lookup"><span data-stu-id="1c621-133">The`/r` option provides the name of the assemblies that are referenced by your code.</span></span> <span data-ttu-id="1c621-134">En este ejemplo, creará un ensamblado privado que solo las aplicaciones podrán usar.</span><span class="sxs-lookup"><span data-stu-id="1c621-134">In this example, you create a private assembly that only your applications can use.</span></span> <span data-ttu-id="1c621-135">Por lo tanto, tiene que guardarlo en el directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1c621-135">Hence, you have to save it in your application's directory.</span></span> <span data-ttu-id="1c621-136">Para información sobre cómo empaquetar e implementar un control para la distribución, vea [Implementación](../../deployment/index.md).</span><span class="sxs-lookup"><span data-stu-id="1c621-136">For more information about packaging and deploying a control for distribution, see [Deployment](../../deployment/index.md).</span></span>

<span data-ttu-id="1c621-137">El siguiente ejemplo muestra el código para `FirstControl`.</span><span class="sxs-lookup"><span data-stu-id="1c621-137">The following sample shows the code for `FirstControl`.</span></span> <span data-ttu-id="1c621-138">El control está incluido en el espacio de nombres `CustomWinControls`.</span><span class="sxs-lookup"><span data-stu-id="1c621-138">The control is enclosed in the namespace `CustomWinControls`.</span></span> <span data-ttu-id="1c621-139">Un espacio de nombres proporciona una agrupación lógica de tipos relacionados.</span><span class="sxs-lookup"><span data-stu-id="1c621-139">A namespace provides a logical grouping of related types.</span></span> <span data-ttu-id="1c621-140">Puede crear el control en un espacio de nombres nuevo o existente.</span><span class="sxs-lookup"><span data-stu-id="1c621-140">You can create your control in a new or existing namespace.</span></span> <span data-ttu-id="1c621-141">En C#, la declaración `using` (en Visual Basic, `Imports`) permite tener acceso desde un espacio de nombres sin utilizar el nombre completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="1c621-141">In C#, the `using` declaration (in Visual Basic, `Imports`) allows types to be accessed from a namespace without using the fully qualified name of the type.</span></span> <span data-ttu-id="1c621-142">En el ejemplo siguiente, la declaración de `using` permite que el código tenga acceso a la clase <xref:System.Windows.Forms.Control> desde <xref:System.Windows.Forms?displayProperty=nameWithType> simplemente <xref:System.Windows.Forms.Control> en lugar de tener que usar el nombre completo <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c621-142">In the following example, the `using` declaration allows code to access the class <xref:System.Windows.Forms.Control> from <xref:System.Windows.Forms?displayProperty=nameWithType> as simply <xref:System.Windows.Forms.Control> instead of having to use the fully qualified name <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>

[!code-csharp[System.Windows.Forms.FirstControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
[!code-vb[System.Windows.Forms.FirstControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]

## <a name="using-the-custom-control-on-a-form"></a><span data-ttu-id="1c621-143">Utilizar el control personalizado en un formulario</span><span class="sxs-lookup"><span data-stu-id="1c621-143">Using the Custom Control on a Form</span></span>

<span data-ttu-id="1c621-144">En el ejemplo siguiente se muestra un formulario simple que usa `FirstControl`.</span><span class="sxs-lookup"><span data-stu-id="1c621-144">The following example shows a simple form that uses `FirstControl`.</span></span> <span data-ttu-id="1c621-145">Crea tres instancias de `FirstControl`, cada una con un valor diferente para la propiedad `TextAlignment`.</span><span class="sxs-lookup"><span data-stu-id="1c621-145">It creates three instances of `FirstControl`, each with a different value for the `TextAlignment` property.</span></span>

#### <a name="to-compile-and-run-this-sample"></a><span data-ttu-id="1c621-146">Para compilar y ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c621-146">To compile and run this sample</span></span>

1. <span data-ttu-id="1c621-147">Guarde el código en el ejemplo siguiente en un archivo de código fuente (SimpleForm.cs o SimpleForms.vb).</span><span class="sxs-lookup"><span data-stu-id="1c621-147">Save the code in the following example to a source file (SimpleForm.cs or SimpleForms.vb).</span></span>

2. <span data-ttu-id="1c621-148">Compile el código fuente en un ensamblado ejecutable ejecutando el siguiente comando desde el directorio que contiene el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="1c621-148">Compile the source code into an executable assembly by executing the following command from the directory that contains the source file.</span></span>

    ```console
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb
    ```

    ```console
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs
    ```

     <span data-ttu-id="1c621-149">CustomWinControls. dll es el ensamblado que contiene la clase `FirstControl`.</span><span class="sxs-lookup"><span data-stu-id="1c621-149">CustomWinControls.dll is the assembly that contains the class `FirstControl`.</span></span> <span data-ttu-id="1c621-150">Este ensamblado debe estar en el mismo directorio que el archivo de origen para el formulario que tiene acceso a él (SimpleForm.cs o SimpleForms.vb).</span><span class="sxs-lookup"><span data-stu-id="1c621-150">This assembly must be in the same directory as the source file for the form that accesses it (SimpleForm.cs or SimpleForms.vb).</span></span>

3. <span data-ttu-id="1c621-151">Ejecute SimpleForm.exe con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="1c621-151">Execute SimpleForm.exe using the following command.</span></span>

    ```console
    SimpleForm
    ```

[!code-csharp[System.Windows.Forms.FirstControl#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
[!code-vb[System.Windows.Forms.FirstControl#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]

## <a name="see-also"></a><span data-ttu-id="1c621-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c621-152">See also</span></span>

- [<span data-ttu-id="1c621-153">Propiedades de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c621-153">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="1c621-154">Eventos de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c621-154">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
