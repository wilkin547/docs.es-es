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
# <a name="how-to-develop-a-simple-windows-forms-control"></a>Cómo: Desarrollar un control de formularios Windows Forms sencillo

Esta sección le guiará a través de los pasos clave para crear un control de Windows Forms personalizado. El control simple desarrollado en este tutorial permite cambiar la alineación de su <xref:System.Windows.Forms.Control.Text%2A> propiedad. No genera ni controla eventos.

### <a name="to-create-a-simple-custom-control"></a>Para crear un control personalizado simple

1. Defina una clase que se derive de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.

    ```vb
    Public Class FirstControl
       Inherits Control

    End Class
    ```

    ```csharp
    public class FirstControl:Control {}
    ```

2. Defina las propiedades. (No es necesario definir propiedades, porque un control hereda muchas propiedades de la clase <xref:System.Windows.Forms.Control>, pero la mayoría de los controles personalizados suelen definir propiedades adicionales). En el fragmento de código siguiente se define una propiedad denominada `TextAlignment` que `FirstControl` utiliza para dar formato a la presentación de la propiedad <xref:System.Windows.Forms.Control.Text%2A> heredada de <xref:System.Windows.Forms.Control>. Para información sobre la definición de propiedades, vea [Introducción a las propiedades](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120)).

     [!code-csharp[System.Windows.Forms.FirstControl#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]

     Al establecer una propiedad que cambia la presentación visual del control, debe invocar el método <xref:System.Windows.Forms.Control.Invalidate%2A> para volver a dibujar el control. <xref:System.Windows.Forms.Control.Invalidate%2A> se define en la <xref:System.Windows.Forms.Control>de la clase base.

3. Invalide el método <xref:System.Windows.Forms.Control.OnPaint%2A> protegido heredado de <xref:System.Windows.Forms.Control> para proporcionar lógica de representación al control. Si no invalida <xref:System.Windows.Forms.Control.OnPaint%2A>, el control no podrá dibujarse a sí mismo. En el fragmento de código siguiente, el método <xref:System.Windows.Forms.Control.OnPaint%2A> muestra la propiedad <xref:System.Windows.Forms.Control.Text%2A> heredada de <xref:System.Windows.Forms.Control> con la alineación especificada por el campo `alignmentValue`.

     [!code-csharp[System.Windows.Forms.FirstControl#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]

4. Proporcione atributos para el control. Los atributos permiten que un diseñador visual muestre el control y sus propiedades y eventos de forma adecuada en el momento del diseño. El siguiente fragmento aplica los atributos a la propiedad `TextAlignment`. En un diseñador como Visual Studio, el <xref:System.ComponentModel.CategoryAttribute.Category%2A> atributo (que se muestra en el fragmento de código) hace que la propiedad se muestre en una categoría lógica. El atributo <xref:System.ComponentModel.DescriptionAttribute.Description%2A> hace que se muestre una cadena descriptiva en la parte inferior de la ventana **propiedades** cuando se selecciona la propiedad `TextAlignment`. Para información sobre los atributos, vea [Atributos en tiempo de diseño para componentes](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).

     [!code-csharp[System.Windows.Forms.FirstControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]

5. (opcional) Proporcione recursos para el control. Puede proporcionar un recurso, como un mapa de bits, para el control mediante una opción de compilador (`/res` para C#) para empaquetar recursos con el control. En tiempo de ejecución, el recurso se puede recuperar utilizando los métodos de la clase <xref:System.Resources.ResourceManager>. Para más información sobre la creación y uso de recursos, vea [Recursos de aplicaciones de escritorio](../../resources/index.md).

6. Compile e implemente el control. Para compilar e implementar `FirstControl,`, realice los siguientes pasos:

    1. Guarde el código del siguiente ejemplo en un archivo de origen (como FirstControl.cs o FirstControl.vb).

    2. Compile el código fuente en un ensamblado y guárdelo en el directorio de la aplicación. Para hacer esto, ejecute el siguiente comando desde el directorio que contiene el archivo de origen.

        ```console
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb
        ```

        ```console
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs
        ```

         La opción del compilador `/t:library` indica al compilador que el ensamblado que se va a crear es una biblioteca (y no un archivo ejecutable). La opción `/out` especifica la ruta de acceso y el nombre del ensamblado. La opción `/r` proporciona el nombre de los ensamblados a los que se hace referencia mediante el código. En este ejemplo, creará un ensamblado privado que solo las aplicaciones podrán usar. Por lo tanto, tiene que guardarlo en el directorio de la aplicación. Para información sobre cómo empaquetar e implementar un control para la distribución, vea [Implementación](../../deployment/index.md).

El siguiente ejemplo muestra el código para `FirstControl`. El control está incluido en el espacio de nombres `CustomWinControls`. Un espacio de nombres proporciona una agrupación lógica de tipos relacionados. Puede crear el control en un espacio de nombres nuevo o existente. En C#, la declaración `using` (en Visual Basic, `Imports`) permite tener acceso desde un espacio de nombres sin utilizar el nombre completo del tipo. En el ejemplo siguiente, la declaración de `using` permite que el código tenga acceso a la clase <xref:System.Windows.Forms.Control> desde <xref:System.Windows.Forms?displayProperty=nameWithType> simplemente <xref:System.Windows.Forms.Control> en lugar de tener que usar el nombre completo <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.

[!code-csharp[System.Windows.Forms.FirstControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
[!code-vb[System.Windows.Forms.FirstControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]

## <a name="using-the-custom-control-on-a-form"></a>Utilizar el control personalizado en un formulario

En el ejemplo siguiente se muestra un formulario simple que usa `FirstControl`. Crea tres instancias de `FirstControl`, cada una con un valor diferente para la propiedad `TextAlignment`.

#### <a name="to-compile-and-run-this-sample"></a>Para compilar y ejecutar este ejemplo

1. Guarde el código en el ejemplo siguiente en un archivo de código fuente (SimpleForm.cs o SimpleForms.vb).

2. Compile el código fuente en un ensamblado ejecutable ejecutando el siguiente comando desde el directorio que contiene el archivo de origen.

    ```console
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb
    ```

    ```console
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs
    ```

     CustomWinControls. dll es el ensamblado que contiene la clase `FirstControl`. Este ensamblado debe estar en el mismo directorio que el archivo de origen para el formulario que tiene acceso a él (SimpleForm.cs o SimpleForms.vb).

3. Ejecute SimpleForm.exe con el siguiente comando.

    ```console
    SimpleForm
    ```

[!code-csharp[System.Windows.Forms.FirstControl#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
[!code-vb[System.Windows.Forms.FirstControl#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]

## <a name="see-also"></a>Vea también

- [Propiedades de los controles de Windows Forms](properties-in-windows-forms-controls.md)
- [Eventos de los controles de Windows Forms](events-in-windows-forms-controls.md)
