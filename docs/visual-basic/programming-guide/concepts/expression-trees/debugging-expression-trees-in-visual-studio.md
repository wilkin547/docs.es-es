---
title: "Depurar árboles de expresión en Visual Studio (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: efbd8c19947c45b3ba15ce7b574000d56526ef45
ms.lasthandoff: 03/13/2017

---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Depurar árboles de expresión en Visual Studio (Visual Basic)
Puede analizar la estructura y contenido de árboles de expresión cuando depura las aplicaciones. Para obtener una introducción rápida de la estructura de árbol de expresión, puede usar el `DebugView` propiedad, que sólo está disponible en modo de depuración. Para obtener más información acerca de la depuración, consulte [depuración en Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio).  
  
 Para representar mejor el contenido de árboles de expresión, el `DebugView` propiedad utiliza los visualizadores de Visual Studio. Para obtener más información, consulte [los visualizadores personalizados de crear](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data).  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Para abrir un visualizador para un árbol de expresión  
  
1.  Haga clic en el icono de lupa que aparece junto a la `DebugView` propiedad de un árbol de expresión en **información sobre datos**, un **inspección** ventana, el **automático** ventana, o la **locales** ventana.  
  
     Se mostrará una lista de visualizadores.  
  
2.  Haga clic en el visualizador que desee usar.  
  
 Cada tipo de expresión se muestra en el visualizador como se describe en las secciones siguientes.  
  
## <a name="parameterexpressions"></a>ParameterExpressions  
 <xref:System.Linq.Expressions.ParameterExpression>los nombres de variables se muestran con un símbolo "$" al principio.</xref:System.Linq.Expressions.ParameterExpression>  
  
 Si un parámetro no tiene un nombre, se asigna un nombre generado automáticamente, como `$var1` o `$var2`.  
  
### <a name="examples"></a>Ejemplos  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer), "num")  
    ```  
  
     Propiedad `DebugView`  
  
     `$num`  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer))  
    ```  
  
     Propiedad `DebugView`  
  
     `$var1`  
  
## <a name="constantexpressions"></a>ConstantExpressions  
 Para <xref:System.Linq.Expressions.ConstantExpression>objetos que representan valores enteros, cadenas, y `null`, se mostrará el valor de la constante.</xref:System.Linq.Expressions.ConstantExpression>  
  
### <a name="examples"></a>Ejemplos  
  
-   `Expression`  
  
    ```vb  
    Dim num as Integer= 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     Propiedad `DebugView`  
  
     10  
  
-   `Expression`  
  
    ```vb  
    Dim num As Double = 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     Propiedad `DebugView`  
  
     10 D.  
  
## <a name="blockexpression"></a>BlockExpression  
 Si el tipo de un <xref:System.Linq.Expressions.BlockExpression>objeto difiere del tipo de la última expresión del bloque, el tipo se muestra en el `DebugInfo` propiedad corchetes angulares (\< y >).</xref:System.Linq.Expressions.BlockExpression> De lo contrario, el tipo de la <xref:System.Linq.Expressions.BlockExpression>no se muestra el objeto.</xref:System.Linq.Expressions.BlockExpression>  
  
### <a name="examples"></a>Ejemplos  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))  
    ```  
  
     Propiedad `DebugView`  
  
     `.Block() {`  
  
     `"test"`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression =   
    Expression.Block(GetType(Object), Expression.Constant("test"))  
    ```  
  
     Propiedad `DebugView`  
  
     `.Block<System.Object>() {`  
  
     `"test"`  
  
     `}`  
  
## <a name="lambdaexpression"></a>Objeto LambdaExpression  
 <xref:System.Linq.Expressions.LambdaExpression>los objetos se muestran junto con sus tipos de delegado.</xref:System.Linq.Expressions.LambdaExpression>  
  
 Si una expresión lambda no tiene un nombre, se asigna un nombre generado automáticamente, como `#Lambda1` o `#Lambda2`.  
  
### <a name="examples"></a>Ejemplos  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))  
    ```  
  
     Propiedad `DebugView`  
  
     `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLamda", Nothing)  
    ```  
  
     Propiedad `DebugView`  
  
     `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
## <a name="labelexpression"></a>LabelExpression  
 Si especifica un valor predeterminado para el <xref:System.Linq.Expressions.LabelExpression>de objeto, este valor se muestra antes de la <xref:System.Linq.Expressions.LabelTarget>objeto.</xref:System.Linq.Expressions.LabelTarget> </xref:System.Linq.Expressions.LabelExpression>  
  
 El `.Label` token indica el inicio de la etiqueta. El `.LabelTarget` token indica el destino al saltar a.  
  
 Si una etiqueta no tiene un nombre, se asigna un nombre generado automáticamente, como `#Label1` o `#Label2`.  
  
### <a name="examples"></a>Ejemplos  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")  
    Dim label1 As BlockExpression = Expression.Block(  
    Expression.Goto(target, Expression.Constant(0)),  
    Expression.Label(target, Expression.Constant(-1)))  
    ```  
  
     Propiedad `DebugView`  
  
     `.Block() {`  
  
     `.Goto SampleLabel { 0 };`  
  
     `.Label`  
  
     `-1`  
  
     `.LabelTarget SampleLabel:`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label()  
    Dim block As BlockExpression = Expression.Block(  
    Expression.Goto(target), Expression.Label(target))  
    ```  
  
     Propiedad `DebugView`  
  
     `.Block() {`  
  
     `.Goto #Label1 { };`  
  
     `.Label`  
  
     `.LabelTarget #Label1:`  
  
     `}`  
  
## <a name="checked-operators"></a>Operadores comprobados  
 Operadores comprobados se muestran con el símbolo "#" delante del operador. Por ejemplo, el operador de adición comprobado se muestra como `#+`.  
  
### <a name="examples"></a>Ejemplos  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.AddChecked(  
    Expression.Constant(1), Expression.Constant(2))  
    ```  
  
     Propiedad `DebugView`  
  
     `1 #+ 2`  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.ConvertChecked(  
    Expression.Constant(10.0), GetType(Integer))  
    ```  
  
     Propiedad `DebugView`  
  
     `#(System.Int32)10D`  
  
## <a name="see-also"></a>Vea también  
 [Árboles de expresión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)   
 [Depurar en Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)   
 [Crear visualizadores personalizados](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)
