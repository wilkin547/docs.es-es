---
title: "C&#243;mo: Exponer propiedades de controles constituyentes | Microsoft Docs"
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
  - "controles constituyentes"
  - "controles [Windows Forms], constituyentes"
  - "controles personalizados [Windows Forms], exponer propiedades"
  - "controles de usuario [Windows Forms], exponer controles constituyentes"
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Exponer propiedades de controles constituyentes
Los controles que forman un control compuesto se denominan *controles constituyentes*.  Estos controles suelen declararse como privados, por lo que no resultan accesibles al programador.  Si desea que las propiedades de estos controles estén disponibles para futuros usuarios, deberá exponerlas a los usuarios.  Para exponer una propiedad de un control constituyente, se crea una propiedad en el control de usuario; a continuación, se utilizan los descriptores de acceso `get` y `set` de esta propiedad para ejecutar el cambio en la propiedad privada del control constituyente.  
  
 Considere un hipotético control de usuario con un botón constituyente denominado `MyButton`.  En este ejemplo, cuando el usuario solicita la propiedad `ConstituentButtonBackColor`, se entrega el valor almacenado en la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> de `MyButton`.  Cuando el usuario asigna un valor a esta propiedad, se pasa automáticamente ese valor a la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> de `MyButton` y se ejecuta el código `set`, lo que cambia el color de `MyButton`.  
  
 En el ejemplo siguiente, se muestra cómo exponer la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> del botón constituyente:  
  
```vb  
Public Property ButtonColor() as System.Drawing.Color  
   Get  
      Return MyButton.BackColor  
   End Get  
   Set(Value as System.Drawing.Color)  
      MyButton.BackColor = Value  
   End Set  
End Property  
```  
  
```csharp  
public Color ButtonColor  
{  
   get  
   {  
      return(myButton.BackColor);  
   }  
   set  
   {  
      myButton.BackColor = value;  
   }  
}  
```  
  
### Para exponer una propiedad de un control constituyente  
  
1.  Cree una propiedad pública para el control de usuario.  
  
2.  En la sección `get` de la propiedad, escriba código que recupere el valor de la propiedad que desea exponer.  
  
3.  En la sección `set` de la propiedad, escriba código que pase el valor de la propiedad a la propiedad expuesta del control constituyente.  
  
## Vea también  
 <xref:System.Windows.Forms.UserControl>   
 [Propiedades de los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)