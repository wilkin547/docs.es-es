---
title: "Cómo: reordenar los campos de un archivo delimitado (LINQ) (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: c451c7db-663b-4daf-b8ba-a2093095d672
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9abb0510ed3944cd80d6658238ef79d64dc0ca27
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-visual-basic"></a>Cómo: reordenar los campos de un archivo delimitado (LINQ) (Visual Basic)
Un archivo de valores separados por comas (CSV) es un archivo de texto que se utiliza a menudo para almacenar datos de la hoja de cálculo u otros datos tabulares que se representan por filas y columnas. Mediante el uso de la <xref:System.String.Split%2A>método para separar los campos, es muy fácil consultar y manipular los archivos CSV mediante LINQ.</xref:System.String.Split%2A> De hecho, la misma técnica puede utilizarse para reordenar partes de cualquier línea estructurado de texto; no se limita a un archivo CSV.  
  
 En el ejemplo siguiente, suponga que las tres columnas representan "last name" los alumnos, "first name" y "ID". Los campos están en orden alfabético según los apellidos de los alumnos. La consulta genera una nueva secuencia en la que la columna de identificador aparece en primer lugar, seguido por una segunda columna que combina el nombre y el apellido del alumno. Las líneas se reordenan según el campo ID. Los resultados se guardan en un archivo nuevo y no se modifican los datos originales.  
  
### <a name="to-create-the-data-file"></a>Para crear el archivo de datos  
  
1.  Copie las líneas siguientes en un archivo de texto sin formato que se denomine spreadsheet1.csv. Guarde el archivo en la carpeta del proyecto.  
  
    ```  
    Adams,Terry,120  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Garcia,Hugo,118  
    Mortensen,Sven,113  
    O'Donnell,Claire,112  
    Omelchenko,Svetlana,111  
    Tucker,Lance,119  
    Tucker,Michael,122  
    Zabokritski,Eugene,121  
    ```  
  
## <a name="example"></a>Ejemplo  
  
```vb  
Class CSVFiles  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data source.  
        Dim lines As String() = System.IO.File.ReadAllLines("../../../spreadsheet1.csv")  
  
        ' Execute the query. Put field 2 first, then  
        ' reverse and combine fields 0 and 1 from the old field  
        Dim lineQuery = From line In lines   
                        Let x = line.Split(New Char() {","})   
                        Order By x(2)   
                        Select x(2) & ", " & (x(1) & " " & x(0))  
  
        ' Execute the query and write out the new file. Note that WriteAllLines  
        ' takes a string array, so ToArray is called on the query.  
        System.IO.File.WriteAllLines("../../../spreadsheet2.csv", lineQuery.ToArray())  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Spreadsheet2.csv written to disk. Press any key to exit")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output to spreadsheet2.csv:  
' 111, Svetlana Omelchenko  
' 112, Claire O'Donnell  
' 113, Sven Mortensen  
' 114, Cesar Garcia  
' 115, Debra Garcia  
' 116, Fadi Fakhouri  
' 117, Hanying Feng  
' 118, Hugo Garcia  
' 119, Lance Tucker  
' 120, Terry Adams  
' 121, Eugene Zabokritski  
' 122, Michael Tucker  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
## <a name="see-also"></a>Vea también  
 [LINQ y cadenas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [LINQ y directorios de archivos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)   
 [Generar XML a partir de archivos CSV](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)
