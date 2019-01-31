---
title: Procedimiento para reordenar los campos de un archivo delimitado (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 4e62d82c-61b7-4f18-b9a1-86723746d7d2
ms.openlocfilehash: 47bdb9a2c3e1042443480bc2308c0039dfb19e74
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738646"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-c"></a><span data-ttu-id="4d5a2-102">Procedimiento para reordenar los campos de un archivo delimitado (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4d5a2-102">How to: Reorder the Fields of a Delimited File (LINQ) (C#)</span></span>
<span data-ttu-id="4d5a2-103">Un archivo de valores separados por comas (CSV) es un archivo de texto que se usa a menudo para almacenar datos de hoja de cálculo u otros datos tabulares que se representan mediante filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="4d5a2-103">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="4d5a2-104">Mediante el uso del método <xref:System.String.Split%2A> para separar los campos, es muy fácil consultar y manipular los archivos CSV con LINQ.</span><span class="sxs-lookup"><span data-stu-id="4d5a2-104">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="4d5a2-105">De hecho, la misma técnica puede usarse para reordenar los elementos de cualquier línea estructurada de texto, no se limita a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="4d5a2-105">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>  
  
 <span data-ttu-id="4d5a2-106">En el ejemplo siguiente, suponga que las tres columnas representan el "apellido", el "nombre" y el "ID" de los alumnos.</span><span class="sxs-lookup"><span data-stu-id="4d5a2-106">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="4d5a2-107">Los campos están en orden alfabético según el apellido de los alumnos.</span><span class="sxs-lookup"><span data-stu-id="4d5a2-107">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="4d5a2-108">La consulta genera una nueva secuencia en la que la columna de identificador aparece en primer lugar, seguida por una segunda columna que combina el nombre y el apellido del alumno.</span><span class="sxs-lookup"><span data-stu-id="4d5a2-108">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="4d5a2-109">Las líneas se reordenan según el campo ID.</span><span class="sxs-lookup"><span data-stu-id="4d5a2-109">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="4d5a2-110">Los resultados se guardan en un archivo nuevo y no se modifican los datos originales.</span><span class="sxs-lookup"><span data-stu-id="4d5a2-110">The results are saved into a new file and the original data is not modified.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="4d5a2-111">Para crear el archivo de datos</span><span class="sxs-lookup"><span data-stu-id="4d5a2-111">To create the data file</span></span>  
  
1.  <span data-ttu-id="4d5a2-112">Copie las líneas siguientes en un archivo de texto sin formato que se denomine spreadsheet1.csv.</span><span class="sxs-lookup"><span data-stu-id="4d5a2-112">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="4d5a2-113">Guarde el archivo en la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4d5a2-113">Save the file in your project folder.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="4d5a2-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d5a2-114">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="4d5a2-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4d5a2-115">Compiling the Code</span></span>  
 <span data-ttu-id="4d5a2-116">Cree un proyecto destinado a .NET Framework versión 3.5 o posterior, con una referencia a System.Core.dll y directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="4d5a2-116">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d5a2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d5a2-117">See also</span></span>

- [<span data-ttu-id="4d5a2-118">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="4d5a2-118">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="4d5a2-119">LINQ y directorios de archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="4d5a2-119">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
- [<span data-ttu-id="4d5a2-120">Cómo: Generar XML a partir de archivos CSV (C#)</span><span class="sxs-lookup"><span data-stu-id="4d5a2-120">How to: Generate XML from CSV Files (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-generate-xml-from-csv-files.md)
