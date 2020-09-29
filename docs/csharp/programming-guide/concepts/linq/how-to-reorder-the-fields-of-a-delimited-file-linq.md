---
title: Procedimiento para reordenar los campos de un archivo delimitado (LINQ) (C#)
description: Obtenga información sobre cómo reorganizar los campos de un archivo .csv de LINQ en C#. En el ejemplo se cambia el orden de las columnas, se realizan combinaciones en ellas y se ordenan las filas por un valor de columna.
ms.date: 07/20/2015
ms.assetid: 4e62d82c-61b7-4f18-b9a1-86723746d7d2
ms.openlocfilehash: 674e6a62112e17107eff690d7656f52488cd08c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203961"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-c"></a><span data-ttu-id="bc083-104">Procedimiento para reordenar los campos de un archivo delimitado (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="bc083-104">How to reorder the fields of a delimited file (LINQ) (C#)</span></span>

<span data-ttu-id="bc083-105">Un archivo de valores separados por comas (CSV) es un archivo de texto que se usa a menudo para almacenar datos de hoja de cálculo u otros datos tabulares que se representan mediante filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="bc083-105">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="bc083-106">Mediante el uso del método <xref:System.String.Split%2A> para separar los campos, es muy fácil consultar y manipular los archivos CSV con LINQ.</span><span class="sxs-lookup"><span data-stu-id="bc083-106">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="bc083-107">De hecho, la misma técnica puede usarse para reordenar los elementos de cualquier línea estructurada de texto, no se limita a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="bc083-107">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>  
  
 <span data-ttu-id="bc083-108">En el ejemplo siguiente, suponga que las tres columnas representan el "apellido", el "nombre" y el "ID" de los alumnos.</span><span class="sxs-lookup"><span data-stu-id="bc083-108">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="bc083-109">Los campos están en orden alfabético según el apellido de los alumnos.</span><span class="sxs-lookup"><span data-stu-id="bc083-109">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="bc083-110">La consulta genera una nueva secuencia en la que la columna de identificador aparece en primer lugar, seguida por una segunda columna que combina el nombre y el apellido del alumno.</span><span class="sxs-lookup"><span data-stu-id="bc083-110">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="bc083-111">Las líneas se reordenan según el campo ID.</span><span class="sxs-lookup"><span data-stu-id="bc083-111">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="bc083-112">Los resultados se guardan en un archivo nuevo y no se modifican los datos originales.</span><span class="sxs-lookup"><span data-stu-id="bc083-112">The results are saved into a new file and the original data is not modified.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="bc083-113">Para crear el archivo de datos</span><span class="sxs-lookup"><span data-stu-id="bc083-113">To create the data file</span></span>  
  
1. <span data-ttu-id="bc083-114">Copie las líneas siguientes en un archivo de texto sin formato que se denomine spreadsheet1.csv.</span><span class="sxs-lookup"><span data-stu-id="bc083-114">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="bc083-115">Guarde el archivo en la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="bc083-115">Save the file in your project folder.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="bc083-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc083-116">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="bc083-117">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="bc083-117">Compiling the Code</span></span>  

<span data-ttu-id="bc083-118">Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="bc083-118">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bc083-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc083-119">See also</span></span>

- [<span data-ttu-id="bc083-120">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="bc083-120">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="bc083-121">LINQ y directorios de archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="bc083-121">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
- [<span data-ttu-id="bc083-122">Procedimiento para generar XML a partir de archivos CSV (C#)</span><span class="sxs-lookup"><span data-stu-id="bc083-122">How to generate XML from CSV files (C#)</span></span>](../../../../standard/linq/generate-xml-csv-files.md)
