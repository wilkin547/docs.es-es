---
title: Procedimiento para reordenar los campos de un archivo delimitado (LINQ) (C#)
description: Obtenga información sobre cómo reorganizar los campos de un archivo .csv de LINQ en C#. En el ejemplo se cambia el orden de las columnas, se realizan combinaciones en ellas y se ordenan las filas por un valor de columna.
ms.date: 07/20/2015
ms.assetid: 4e62d82c-61b7-4f18-b9a1-86723746d7d2
ms.openlocfilehash: 3ebc56b418d2732a296896a19d770136a56e2fbb
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103407"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-c"></a>Procedimiento para reordenar los campos de un archivo delimitado (LINQ) (C#)
Un archivo de valores separados por comas (CSV) es un archivo de texto que se usa a menudo para almacenar datos de hoja de cálculo u otros datos tabulares que se representan mediante filas y columnas. Mediante el uso del método <xref:System.String.Split%2A> para separar los campos, es muy fácil consultar y manipular los archivos CSV con LINQ. De hecho, la misma técnica puede usarse para reordenar los elementos de cualquier línea estructurada de texto, no se limita a un archivo CSV.  
  
 En el ejemplo siguiente, suponga que las tres columnas representan el "apellido", el "nombre" y el "ID" de los alumnos. Los campos están en orden alfabético según el apellido de los alumnos. La consulta genera una nueva secuencia en la que la columna de identificador aparece en primer lugar, seguida por una segunda columna que combina el nombre y el apellido del alumno. Las líneas se reordenan según el campo ID. Los resultados se guardan en un archivo nuevo y no se modifican los datos originales.  
  
### <a name="to-create-the-data-file"></a>Para crear el archivo de datos  
  
1. Copie las líneas siguientes en un archivo de texto sin formato que se denomine spreadsheet1.csv. Guarde el archivo en la carpeta del proyecto.  
  
    ```csv  
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
  
```csharp  
class CSVFiles  
{  
    static void Main(string[] args)  
    {  
        // Create the IEnumerable data source  
        string[] lines = System.IO.File.ReadAllLines(@"../../../spreadsheet1.csv");  
  
        // Create the query. Put field 2 first, then  
        // reverse and combine fields 0 and 1 from the old field  
        IEnumerable<string> query =  
            from line in lines  
            let x = line.Split(',')  
            orderby x[2]  
            select x[2] + ", " + (x[1] + " " + x[0]);  
  
        // Execute the query and write out the new file. Note that WriteAllLines  
        // takes a string[], so ToArray is called on the query.  
        System.IO.File.WriteAllLines(@"../../../spreadsheet2.csv", query.ToArray());  
  
        Console.WriteLine("Spreadsheet2.csv written to disk. Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output to spreadsheet2.csv:  
111, Svetlana Omelchenko  
112, Claire O'Donnell  
113, Sven Mortensen  
114, Cesar Garcia  
115, Debra Garcia  
116, Fadi Fakhouri  
117, Hanying Feng  
118, Hugo Garcia  
119, Lance Tucker  
120, Terry Adams  
121, Eugene Zabokritski  
122, Michael Tucker  
 */  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.
  
## <a name="see-also"></a>Consulte también

- [LINQ y cadenas (C#)](./linq-and-strings.md)
- [LINQ y directorios de archivos (C#)](./linq-and-file-directories.md)
- [Procedimiento para generar XML a partir de archivos CSV (C#)](./how-to-generate-xml-from-csv-files.md)
