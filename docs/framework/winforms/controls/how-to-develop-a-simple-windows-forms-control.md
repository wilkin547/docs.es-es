---
title: "C&#243;mo: Desarrollar un control de formularios Windows Forms sencillo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Control (clase), Windows Forms"
  - "controles [Windows Forms]"
  - "controles personalizados [Windows Forms], crear controles simples mediante código"
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Desarrollar un control de formularios Windows Forms sencillo
En esta sección se ofrece un tutorial que describe los pasos básicos para crear un control de formularios Windows Forms personalizado.  El control sencillo desarrollado en este tutorial permite modificar la alineación de su propiedad <xref:System.Windows.Forms.Control.Text%2A>.  No provoca ni controla eventos.  
  
### Para crear un control personalizado sencillo  
  
1.  Defina una clase que se derive de <xref:System.Windows.Forms.Control?displayProperty=fullName>.  
  
    ```vb  
    Public Class FirstControl  
       Inherits Control  
  
    End Class  
    ```  
  
    ```csharp  
    public class FirstControl:Control{}  
    ```  
  
2.  Defina propiedades.  \(No es necesario definir propiedades, ya que los controles heredan muchas propiedades de la clase <xref:System.Windows.Forms.Control>, aunque para la mayoría de los controles personalizados se suelen definir propiedades adicionales.\) En el fragmento de código siguiente se define una propiedad denominada `TextAlignment` que`FirstControl` utiliza para dar formato a la apariencia de la propiedad <xref:System.Windows.Forms.Control.Text%2A> heredada de <xref:System.Windows.Forms.Control>.  Para obtener más información sobre la definición de propiedades, vea [Properties Overview](../Topic/Properties%20Overview.md).  
  
     [!code-csharp[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]  
  
     Cuando se establece una propiedad que cambia la apariencia visual del control, se debe invocar el método <xref:System.Windows.Forms.Control.Invalidate%2A> para volver a dibujar el control.  <xref:System.Windows.Forms.Control.Invalidate%2A> se define en la clase base <xref:System.Windows.Forms.Control>.  
  
3.  Reemplace el método protegido <xref:System.Windows.Forms.Control.OnPaint%2A> heredado de <xref:System.Windows.Forms.Control> para proporcionar lógica de representación al control.  Si no reemplaza <xref:System.Windows.Forms.Control.OnPaint%2A>, el control no podrá dibujarse a sí mismo.  En el fragmento de código siguiente, el método <xref:System.Windows.Forms.Control.OnPaint%2A> muestra la propiedad <xref:System.Windows.Forms.Control.Text%2A> heredada de <xref:System.Windows.Forms.Control> con la alineación especificada por el campo `alignmentValue`.  
  
     [!code-csharp[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]  
  
4.  Proporcione atributos para el control.  Los atributos permite a los diseñadores visuales mostrar el control y sus propiedades y evento correctamente en tiempo de diseño.  El fragmento de código siguiente aplica atributos a la propiedad `TextAlignment`.  En un diseñador como Visual Studio, el atributo <xref:System.ComponentModel.CategoryAttribute.Category%2A> \(que aparece en el fragmento de código\) hace que se muestre la propiedad en una categoría lógica.  El atributo <xref:System.ComponentModel.DescriptionAttribute.Description%2A> hace que se muestre una cadena descriptiva en la parte inferior de la ventana **Propiedades** cuando se selecciona la propiedad `TextAlignment`.  Para obtener más información sobre controles, vea [Design\-Time Attributes for Components](../Topic/Design-Time%20Attributes%20for%20Components.md).  
  
     [!code-csharp[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]  
  
5.  \(opcional\) Proporcione recursos para el control.  Para proporcionar un recurso, como un mapa de bits, al control, utilice una opción del compilador \(`/res` para C\#\) para empaquetar recursos con el control.  En tiempo de ejecución, el recurso se puede recuperar utilizando los métodos de la clase <xref:System.Resources.ResourceManager>.  Para obtener más información sobre cómo crear y utilizar los recursos, vea [Recursos de aplicaciones de escritorio](../../../../docs/framework/resources/index.md).  
  
6.  Compile e implemente el control.  Para compilar e implementar `FirstControl,`, realice los pasos siguientes.  
  
    1.  Guarde el código del siguiente ejemplo en un archivo de código fuente \(como FirstControl.cs o FirstControl.vb\).  
  
    2.  Compile el código fuente en un ensamblado y guárdelo en el directorio de la aplicación.  Para ello, ejecute el siguiente comando desde el directorio que contiene el archivo de código fuente.  
  
        ```vb  
        vbc /t:library /out:[path to your application's directory]/CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll FirstControl.vb  
        ```  
  
        ```csharp  
        csc /t:library /out:[path to your application's directory]/CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll FirstControl.cs  
        ```  
  
         La opción del compilador `/t:library` indica al compilador que el ensamblado que se está creando es una biblioteca \(y no un ejecutable\).  La opción `/out` especifica la ruta de acceso y el nombre del ensamblado.  La opción `/r` indica el nombre de los ensamblados a los que hace referencia el código.  En este ejemplo, se crea un ensamblado privado que sólo pueden utilizar sus aplicaciones.  Por tanto, debe guardarlo en el directorio de su aplicación.  Para obtener más información sobre cómo empaquetar e implementar un control para la distribución, vea [Implementación](../../../../docs/framework/deployment/net-framework-and-applications.md).  
  
 En el siguiente ejemplo se muestra el código de `FirstControl`.  El control está incluido en el espacio de nombres `CustomWinControls`.  Un espacio de nombres proporciona una agrupación lógica de tipos relacionados.  El control se puede crear en un espacio de nombres nuevo o en uno existente.  En C\#, la declaración `using` \(en Visual Basic, `Imports`\) permite el acceso a los tipos desde un espacio de nombres sin utilizar el nombre completo del tipo.  En el ejemplo siguiente, la declaración `using` permite al código tener acceso a la clase <xref:System.Windows.Forms.Control> desde <xref:System.Windows.Forms?displayProperty=fullName> simplemente como <xref:System.Windows.Forms.Control> en lugar de tener que usar el nombre completo de <xref:System.Windows.Forms.Control?displayProperty=fullName>.  
  
 [!code-csharp[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
 [!code-vb[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]  
  
## Utilizar el control personalizado en un formulario  
 En el siguiente ejemplo se muestra un formulario sencillo que utiliza `FirstControl`.  Crea tres instancias de `FirstControl`, cada una con un valor distinto de la propiedad `TextAlignment`.  
  
#### Para compilar y ejecutar este ejemplo  
  
1.  Guarde el código del siguiente ejemplo en un archivo de código fuente \(SimpleForm.cs o SimpleForms.vb\).  
  
2.  Compile el código fuente en un ensamblado ejecutable; para ello, ejecute el siguiente comando desde el directorio que contiene el archivo de código fuente.  
  
    ```vb  
    vbc /r:CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll SimpleForm.vb  
    ```  
  
    ```csharp  
    csc /r:CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll SimpleForm.cs  
    ```  
  
     CustomWinControls.dll es el ensamblado que contiene la clase`FirstControl`.  Este ensamblado debe encontrarse en el mismo directorio que el archivo de código fuente del formulario que tiene acceso a él. \(SimpleForm.cs o SimpleForms.vb\).  
  
3.  Ejecute SimpleForm.exe con el siguiente comando.  
  
    ```  
    SimpleForm  
    ```  
  
 [!code-csharp[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
 [!code-vb[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]  
  
## Vea también  
 [Propiedades de los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [Eventos de los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)