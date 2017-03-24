---
title: "Cómo: crear y utilizar ensamblados desde la línea de comandos (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 363bca806736e5540165ea96e9b4fe60d0968098
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>Cómo: crear y utilizar ensamblados desde la línea de comandos (Visual Basic)
Un ensamblado o una biblioteca de vínculos dinámica (DLL), se vincula al programa en tiempo de ejecución. Para ilustrar la creación y uso de una DLL, considere el siguiente escenario:  
  
-   `MathLibrary.DLL`: El archivo de biblioteca que contiene los métodos para llamar en tiempo de ejecución. En este ejemplo, la DLL contiene dos métodos, `Add` y `Multiply`.  
  
-   `Add`: El archivo de origen que contiene el método `Add`. Devuelve la suma de sus parámetros. La clase `AddClass` que contiene el método `Add` es un miembro del espacio de nombres `UtilityMethods`.  
  
-   `Mult`: El código fuente que contiene el método `Multiply`. Devuelve el producto de sus parámetros. La clase `MultiplyClass` que contiene el método `Multiply` también es un miembro del espacio de nombres `UtilityMethods`.  
  
-   `TestCode`: El archivo que contiene el `Main` método. Utiliza los métodos en el archivo DLL para calcular la suma y el producto de los argumentos de tiempo de ejecución.  
  
## <a name="example"></a>Ejemplo  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 Este archivo contiene el algoritmo que utiliza los métodos de la DLL, `Add` y `Multiply`. Empieza analizando los argumentos especificados en la línea de comandos `num1` y `num2`. A continuación, calcula la suma mediante el uso de la `Add` método en el `AddClass` clase y el producto mediante el uso de la `Multiply` método en la `MultiplyClass` clase.  
  
 Observe que el `Imports` instrucción al principio del archivo permite utilizar los nombres de clase sin calificar para hacer referencia a los métodos de la DLL en tiempo de compilación, como sigue:  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 En caso contrario, deberá utilizar los nombres completos, como sigue:  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a>Execution  
 Para ejecutar el programa, escriba el nombre del archivo EXE seguido de dos números, como sigue:  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para generar el archivo `MathLibrary.DLL`, compile los dos archivos `Add` y `Mult` mediante el uso de la línea de comandos.  
  
```vb  
vbc /target:library /out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 El [/target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) opción del compilador indica al compilador que genere un archivo DLL en lugar de un archivo EXE. El [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) opción del compilador seguida de un nombre de archivo se utiliza para especificar el nombre del archivo DLL. De lo contrario, el compilador usa el primer archivo (`Add.vb`) como el nombre del archivo DLL.  
  
 Para generar el archivo ejecutable, `TestCode.exe`, utilice la siguiente línea de comandos:  
  
```vb  
vbc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.vb  
```  
  
 El **/out** opción indica al compilador que genere un archivo EXE y especifica el nombre del archivo de salida (`TestCode.exe`). Esta opción del compilador es opcional. El [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) opción del compilador especifica el archivo DLL o los archivos que utiliza el programa.  
  
 Para obtener más información sobre la compilación desde la línea de comandos, vea y [compilar desde la línea de comandos](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
## <a name="see-also"></a>Vea también  
 [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)   
 [Ensamblados y caché Global de ensamblados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Crear una clase para contener funciones de archivos DLL](http://msdn.microsoft.com/library/e08e4c34-0223-45f7-aa55-a3d8dd979b0f)
