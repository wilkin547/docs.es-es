---
title: "C&#243;mo: Proporcionar un mapa de bits del cuadro de herramientas para un control | Microsoft Docs"
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
  - "mapas de bits [Windows Forms], controles personalizados"
  - "controles personalizados [Windows Forms], mapas de bits del cuadro de herramientas"
  - "Cuadro de herramientas [formularios Windows Forms], agregar mapas de bits para controles personalizados"
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# C&#243;mo: Proporcionar un mapa de bits del cuadro de herramientas para un control
Si desea que un icono especial para el control aparezca en el **Cuadro de herramientas**, puede especificar una imagen particular utilizando <xref:System.Drawing.ToolboxBitmapAttribute>.  Esta clase es un *atributo*, un tipo de clase especial que se puede asociar a otras clases.  Para obtener más información sobre los atributos, vea [NOT IN BUILD: Attributes Overview in Visual Basic](http://msdn.microsoft.com/es-es/0d0cff64-892d-4f57-83bd-bef388553d4f) para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] y [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md) para [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].  
  
 Mediante <xref:System.Drawing.ToolboxBitmapAttribute>, puede especificar una cadena que indique la ruta de acceso y el nombre de archivo para un mapa de bits de 16 por 16 píxeles.  Este mapa de bits aparecerá junto al control cuando se agregue al **Cuadro de herramientas**.  También puede especificar un <xref:System.Type>, en cuyo caso se carga el mapa de bits asociado a ese tipo.  Si especifica tanto el parámetro <xref:System.Type> como una cadena, el control busca un recurso de imagen con el nombre especificado por el parámetro de cadena en el ensamblado que contiene el tipo especificado por el parámetro <xref:System.Type>.  
  
### Para especificar un mapa de bits de cuadro de herramientas a un control  
  
1.  Agregue <xref:System.Drawing.ToolboxBitmapAttribute> a la declaración de clase del control antes de la palabra clave `Class` para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], y sobre la declaración de clase para [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].  
  
    ```vb  
    ' Specifies the bitmap associated with the Button type.  
    <ToolboxBitmap(GetType(Button))> Class MyControl1  
    ' Specifies a bitmap file.  
    End Class  
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _  
       Class MyControl2  
    End Class  
    ' Specifies a type that indicates the assembly to search, and the name   
    ' of an image resource to look for.  
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl  
    End Class  
    ```  
  
    ```csharp  
    // Specifies the bitmap associated with the Button type.  
    [ToolboxBitmap(typeof(Button))]  
    class MyControl1 : UserControl  
    {  
    }  
    // Specifies a bitmap file.  
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]  
    class MyControl2 : UserControl  
    {  
    }  
    // Specifies a type that indicates the assembly to search, and the name   
    // of an image resource to look for.  
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]  
    class MyControl : UserControl  
    {  
    }  
    ```  
  
2.  Recompile el proyecto.  
  
    > [!NOTE]
    >  El mapa de bits no aparece en el cuadro de herramientas para los controles y componentes generados automáticamente.  Para ver el mapa de bits, recargue el control mediante el cuadro de diálogo **Elegir elementos del cuadro de herramientas**.  Para obtener más información, vea [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
## Vea también  
 <xref:System.Drawing.ToolboxBitmapAttribute>   
 [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)   
 [Desarrollar controles de formularios Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [Atributos](../Topic/Attributes%20\(Visual%20Basic\)1.md)   
 [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)