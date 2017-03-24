---
title: "Cómo: determinar si un archivo es un ensamblado (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
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
ms.openlocfilehash: 2e58363369ae4420879310bf09ed89cdd4f5b5cc
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a>Cómo: determinar si un archivo es un ensamblado (Visual Basic)
Un archivo es un ensamblado si y solo si se administra y contiene una entrada de ensamblado en sus metadatos. Para obtener más información sobre ensamblados y metadatos, vea el tema [manifiesto del ensamblado](https://msdn.microsoft.com/library/1w45z383).  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>Cómo determinar manualmente si un archivo es un ensamblado  
  
1.  Iniciar el [Ildasm.exe (Desensamblador IL)](https://msdn.microsoft.com/library/f7dy01k1).  
  
2.  Cargar el archivo que desea probar.  
  
3.  Si **ILDASM** informes que el archivo no es un archivo ejecutable portable (PE), entonces no es un ensamblado. Para obtener más información, vea el tema [Cómo: ver el contenido de ensamblado](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709).  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>Cómo determinar mediante programación si un archivo es un ensamblado  
  
1.  Llame a la <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>método, pasando la ruta de acceso completa y el nombre del archivo que se está probando.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A>  
  
2.  Si un <xref:System.BadImageFormatException>excepción, el archivo no es un ensamblado.</xref:System.BadImageFormatException>  
  
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
  
 El <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>método carga el archivo de prueba y, a continuación, lo libera una vez que se lee la información.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName>   
 [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)   
 [Ensamblados y caché Global de ensamblados (Visual Basic)](index.md)
