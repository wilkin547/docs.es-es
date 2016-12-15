---
title: "Valores de las variables de objeto (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos de datos [Visual Basic], variable de objeto"
  - "variables de objeto, valores"
  - "valores, de variables de objeto"
  - "variables [Visual Basic], objeto"
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Valores de las variables de objeto (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Una variable de [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md) puede hacer referencia a datos de cualquier tipo.  El valor que se le da a una variable `Object` se guarda en algún lugar de la memoria fuera de la variable; lo que contiene la variable es un puntero a los datos.  
  
## Funciones del clasificador de objetos  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona funciones que devuelven información de la referencia a que remite una variable `Object`, como se muestra en la tabla siguiente.  
  
|Función|Devuelve True si la variable Object hace referencia a|  
|-------------|-----------------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Una matriz de valores, en lugar de un valor único.|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|Un valor [Date \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/date-data-type.md) o una cadena que puede interpretarse como un valor de fecha y hora.|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Un objeto de tipo <xref:System.DBNull> que representa datos que faltan o que no existen.|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Un objeto de excepción que se deriva de <xref:System.Exception>.|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Nothing](../../../../visual-basic/language-reference/nothing.md), es decir que no hay ningún objeto asignado actualmente a la variable.|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Un número o una cadena que puede interpretarse como un número.|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Un tipo de referencia \(como una cadena, matriz, delegado o tipo de clase\).|  
  
 Puede utilizar estas funciones para impedir que se envíe un valor no válido a una operación o a un procedimiento.  
  
## Operador TypeOf  
 También puede utilizar el operador [TypeOf \(Operador\)](../../../../visual-basic/language-reference/operators/typeof-operator.md) para averiguar si una variable de objeto hace referencia en ese momento a un tipo de datos específico.  La expresión `TypeOf`...`Is` se evalúa como `True` si el tipo en tiempo de ejecución del operando se deriva del tipo especificado o lo implementa.  
  
 En el siguiente ejemplo se utiliza `TypeOf` en variables de objeto que hacen referencia a tipos de valor y de referencia:  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 Como resultado del ejemplo anterior, se escriben las siguientes líneas en la ventana **Depuración**:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 La variable de objeto `num` hace referencia a datos de tipo `Integer` y `frm` hace referencia a un objeto de clase <xref:System.Windows.Forms.Form>.  
  
## Matrices de objetos  
 Puede declarar y utilizar matrices de variables `Object`,  lo cual puede resultarle útil si necesita controlar varios tipos de datos y clases de objetos.  Todos los elementos de una matriz deben tener declarado el mismo tipo de datos.  Si este tipo de datos se declara como `Object`, se pueden almacenar en la matriz instancias de clase y objetos junto con otros tipos de datos.  
  
## Vea también  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Cómo: Hacer referencia a la instancia actual de un objeto](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)   
 [Cómo: Determinar el tipo al que hace referencia una variable de objeto](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)   
 [Cómo: Determinar si dos objetos están relacionados](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [Cómo: Determinar si dos objetos son idénticos](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)   
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)