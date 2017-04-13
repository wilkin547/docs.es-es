---
title: "Implementaci&#243;n de m&#233;todos en controles personalizados | Microsoft Docs"
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
  - "controles de usuario [Windows Forms], el método de implementación"
  - "controles personalizados [Windows Forms], la sobrecarga de métodos"
  - "controles personalizados [Windows Forms], implementación de método"
  - "métodos [Windows Forms]"
  - "métodos [Windows Forms], controles personalizados"
ms.assetid: 35d14fca-4bb4-4a27-8211-1f7a98ea27de
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Implementaci&#243;n de m&#233;todos en controles personalizados
Un método se implementa en un control de la misma manera que se implementa en cualquier otro componente.  
  
 En Visual Basic, si se necesita un método para devolver un valor, se implementa como `Public Function`. Si no se devuelve ningún valor, se implementa como `Public Sub`. Los métodos se declaran mediante la siguiente sintaxis:  
  
```vb  
Public Function ConvertMatterToEnergy(Matter as Integer) As Integer  
   ' Conversion code goes here.  
End Function  
```  
  
 Como las funciones devuelven un valor, deben especificar un tipo de valor devuelto, por ejemplo, entero, cadena, objeto, etc. También se deben especificar los argumentos `Function` o `Sub` que toma el procedimiento, si corresponde.  
  
 C# no realiza distinciones entre funciones y procedimientos como sí hace Visual Basic. Un método devuelve un valor o devuelve `void`. La sintaxis para declarar un método público de C# es:  
  
```csharp  
public int ConvertMatterToEnergy(int matter)  
{  
   // Conversion code goes here.  
}  
```  
  
 Cuando declare un método, declare todos sus argumentos como tipos de datos explícitos siempre que sea posible. Los argumentos que toman referencias de objeto se deben declarar como tipos de clase específicos, por ejemplo, `As Widget` en lugar de `As Object`. En Visual Basic, la opción predeterminada `Option Strict` aplica automáticamente esta regla.  
  
 Los argumentos con tipo permiten capturar muchos errores del desarrollador en el compilador, en lugar de en tiempo de ejecución. El compilador siempre captura errores, mientras que las pruebas en tiempo de ejecución solo son buenas si el conjunto de pruebas lo es.  
  
## <a name="overloaded-methods"></a>Métodos sobrecargados  
 Si quiere que los usuarios del control puedan suministrar diferentes combinaciones de parámetros a un método, proporcione varias sobrecargas del método usando tipos de datos explícitos. Evite crear parámetros declarados `As Object` que puedan contener algún tipo de datos, porque esto podría provocar errores que quizás no se capturen en las pruebas.  
  
> [!NOTE]
>  El tipo de datos universal en Common Language Runtime es `Object` en lugar de `Variant`. `Variant` se ha quitado del lenguaje.  
  
 Por ejemplo, el método `Spin` de un control `Widget` hipotético podría permitir especificar directamente la dirección y la velocidad de giro, o especificar otro objeto `Widget` desde el cual se absorba el momento angular:  
  
```vb  
Overloads Public Sub Spin( _  
   ByVal SpinDirection As SpinDirectionsEnum, _  
   ByVal RevolutionsPerSecond As Double)  
   ' Implementation code here.  
End Sub  
Overloads Public Sub Spin(ByVal Driver As Widget) _  
   ' Implementation code here.  
End Sub  
```  
  
```csharp  
public void Spin(SpinDirectionsEnum spinDirection, double revolutionsPerSecond)  
{  
   // Implementation code here.  
}  
  
public void Spin(Widget driver)  
{  
   // Implementation code here.  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Eventos](../../../../docs/standard/events/index.md)   
 [Propiedades de controles de Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)