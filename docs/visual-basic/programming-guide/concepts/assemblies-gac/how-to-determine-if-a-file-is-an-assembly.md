---
title: 'Cómo: determinar si un archivo es un ensamblado (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
ms.openlocfilehash: 84d45cea4a2557350edacd5f05b12c8ffcac4df8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643253"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a>Cómo: determinar si un archivo es un ensamblado (Visual Basic)
Un archivo es un ensamblado únicamente si está administrado y contiene una entrada de ensamblado en sus metadatos. Para más información sobre ensamblados y metadatos, vea el tema [Manifiesto del ensamblado](../../../../framework/app-domains/assembly-manifest.md).  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>Cómo determinar manualmente si un archivo es un ensamblado  
  
1.  Inicie [Ildasm.exe (el desensamblador de lenguaje intermedio)](https://msdn.microsoft.com/library/f7dy01k1).  
  
2.  Cargue el archivo que quiere probar.  
  
3.  Si **ILDASM** notifica que el archivo no es un archivo ejecutable portable (PE), entonces no es un ensamblado. Para obtener más información, vea el tema [Cómo: Ver el contenido de un ensamblado](../../../../framework/app-domains/how-to-view-assembly-contents.md).  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>Cómo determinar mediante programación si un archivo es un ensamblado  
  
1.  Llame al método <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>; para ello, pase el nombre y la ruta de acceso de archivo completa del archivo que está probando.  
  
2.  Si se genera una excepción <xref:System.BadImageFormatException>, el archivo no es un ensamblado.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se prueba un archivo DLL para ver si es un ensamblado.  
  
```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```
  
 El método <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> carga el archivo de prueba y, después, lo libera cuando se lee la información.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Reflection.AssemblyName>  
 [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)  
 [Ensamblados y caché global de ensamblados (Visual Basic)](index.md)
