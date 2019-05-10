---
title: Procedimiento Crear y usar ensamblados desde la línea de comandos (Visual Basic)
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: d58109dfbb03b752f4a46f895fa1093e4f37df71
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624775"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>Procedimiento Crear y usar ensamblados desde la línea de comandos (Visual Basic)
Un ensamblado, o una biblioteca de vínculos dinámicos (DLL), se vincula al programa en tiempo de ejecución. Para ilustrar la creación y uso de una DLL, considere el siguiente escenario:  
  
- `MathLibrary.DLL`: el archivo de biblioteca que contiene los métodos que se van a llamar en tiempo de ejecución. En este ejemplo, la DLL contiene dos métodos, `Add` y `Multiply`.  
  
- `Add`: el archivo de origen que contiene el método `Add`. Devuelve la suma de sus parámetros. La clase `AddClass` que contiene el método `Add` es un miembro del espacio de nombres `UtilityMethods`.  
  
- `Mult`: el código fuente que contiene el método `Multiply`. Devuelve el producto de sus parámetros. La clase `MultiplyClass` que contiene el método `Multiply` también es un miembro del espacio de nombres `UtilityMethods`.  
  
- `TestCode`: el archivo que contiene el método `Main`. Usa los métodos en el archivo DLL para calcular la suma y el producto de los argumentos de tiempo de ejecución.  
  
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
  
 Este archivo contiene el algoritmo que usa los métodos de la DLL, `Add` y `Multiply`. Empieza analizando los argumentos especificados en la línea de comandos, `num1` y `num2`. Después, calcula la suma mediante el método `Add` de la clase `AddClass`, y el producto mediante el método `Multiply` de la clase `MultiplyClass`.  
  
 Tenga en cuenta que el `Imports` instrucción al principio del archivo le permite usar los nombres de clase no completos para hacer referencia a los métodos de la DLL en tiempo de compilación, como se indica a continuación:  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 En caso contrario, deberá usar los nombres completos, como se muestra a continuación:  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a>Execution  
 Para ejecutar el programa, escriba el nombre del archivo EXE, seguido de dos números, de esta forma:  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para generar el archivo `MathLibrary.DLL`, compile los dos archivos `Add` y `Mult` mediante la línea de comandos siguiente.  
  
```console  
vbc -target:library -out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 El [-destino (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) opción del compilador indica al compilador que genere un archivo DLL en lugar de un archivo EXE. El [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) opción del compilador seguido por un nombre de archivo se usa para especificar el nombre del archivo DLL. De lo contrario, el compilador usa el primer archivo (`Add.vb`) como el nombre de la DLL.  
  
 Para compilar el archivo ejecutable, `TestCode.exe`, use la siguiente línea de comandos:  
  
```console  
vbc -out:TestCode.exe -reference:MathLibrary.DLL TestCode.vb  
```  
  
 El **-out** opción del compilador indica al compilador que genere un archivo EXE y especifica el nombre del archivo de salida (`TestCode.exe`). Esta opción del compilador es opcional. El [-referencia (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) opción del compilador especifica el archivo o archivos DLL que utiliza el programa.  
  
 Para obtener más información sobre la compilación desde la línea de comandos, vea y [compilar desde la línea de comandos](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
## <a name="see-also"></a>Vea también

- [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)
- [Ensamblados de .NET](../../../../standard/assembly/index.md)
- [Creación de una clase para contener funciones de archivos DLL](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
