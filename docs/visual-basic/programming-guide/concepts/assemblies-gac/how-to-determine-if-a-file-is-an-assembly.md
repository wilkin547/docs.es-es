---
title: Procedimiento Determinar si un archivo es un ensamblado (Visual Basic)
ms.date: 07/20/2015
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
ms.openlocfilehash: 47ac7f29509af86819006a4394ca661140b95ab0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316068"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a>Procedimiento Determinar si un archivo es un ensamblado (Visual Basic)
Un archivo es un ensamblado únicamente si está administrado y contiene una entrada de ensamblado en sus metadatos. Para más información sobre ensamblados y metadatos, vea el tema [Manifiesto del ensamblado](../../../../framework/app-domains/assembly-manifest.md).  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>Cómo determinar manualmente si un archivo es un ensamblado  
  
1. Inicie [Ildasm.exe (el desensamblador de lenguaje intermedio)](../../../../framework/tools/ildasm-exe-il-disassembler.md).  
  
2. Cargue el archivo que quiere probar.  
  
3. Si **ILDASM** notifica que el archivo no es un archivo ejecutable portable (PE), entonces no es un ensamblado. Para obtener más información, vea el tema [Cómo: Consulta del contenido de un ensamblado](../../../../framework/app-domains/how-to-view-assembly-contents.md).  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>Cómo determinar mediante programación si un archivo es un ensamblado  
  
1. Llame al método <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>; para ello, pase el nombre y la ruta de acceso de archivo completa del archivo que está probando.  
  
2. Si se genera una excepción <xref:System.BadImageFormatException>, el archivo no es un ensamblado.  
  
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

- <xref:System.Reflection.AssemblyName>
- [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)
- [Ensamblados y caché global de ensamblados (Visual Basic)](index.md)
