---
description: 'Más información acerca de cómo: reordenar los campos de un archivo delimitado (LINQ) (Visual Basic)'
title: Procedimiento para reordenar los campos de un archivo delimitado (LINQ)
ms.date: 07/20/2015
ms.assetid: c451c7db-663b-4daf-b8ba-a2093095d672
ms.openlocfilehash: bfb06c396dbe33628ea146622c9c4ebe9534aae4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435010"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-visual-basic"></a><span data-ttu-id="edd1d-103">Cómo: reordenar los campos de un archivo delimitado (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edd1d-103">How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="edd1d-104">Un archivo de valores separados por comas (CSV) es un archivo de texto que se usa a menudo para almacenar datos de hoja de cálculo u otros datos tabulares que se representan mediante filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="edd1d-104">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="edd1d-105">Mediante el uso del método <xref:System.String.Split%2A> para separar los campos, es muy fácil consultar y manipular los archivos CSV con LINQ.</span><span class="sxs-lookup"><span data-stu-id="edd1d-105">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="edd1d-106">De hecho, la misma técnica puede usarse para reordenar los elementos de cualquier línea estructurada de texto, no se limita a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="edd1d-106">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>

<span data-ttu-id="edd1d-107">En el ejemplo siguiente, suponga que las tres columnas representan el "apellido", el "nombre" y el "ID" de los alumnos.</span><span class="sxs-lookup"><span data-stu-id="edd1d-107">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="edd1d-108">Los campos están en orden alfabético según el apellido de los alumnos.</span><span class="sxs-lookup"><span data-stu-id="edd1d-108">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="edd1d-109">La consulta genera una nueva secuencia en la que la columna de identificador aparece en primer lugar, seguida por una segunda columna que combina el nombre y el apellido del alumno.</span><span class="sxs-lookup"><span data-stu-id="edd1d-109">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="edd1d-110">Las líneas se reordenan según el campo ID.</span><span class="sxs-lookup"><span data-stu-id="edd1d-110">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="edd1d-111">Los resultados se guardan en un archivo nuevo y no se modifican los datos originales.</span><span class="sxs-lookup"><span data-stu-id="edd1d-111">The results are saved into a new file and the original data is not modified.</span></span>

### <a name="to-create-the-data-file"></a><span data-ttu-id="edd1d-112">Para crear el archivo de datos</span><span class="sxs-lookup"><span data-stu-id="edd1d-112">To create the data file</span></span>

1. <span data-ttu-id="edd1d-113">Copie las líneas siguientes en un archivo de texto sin formato que se denomine spreadsheet1.csv.</span><span class="sxs-lookup"><span data-stu-id="edd1d-113">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="edd1d-114">Guarde el archivo en la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="edd1d-114">Save the file in your project folder.</span></span>

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

## <a name="example"></a><span data-ttu-id="edd1d-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edd1d-115">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="edd1d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="edd1d-116">See also</span></span>

- [<span data-ttu-id="edd1d-117">LINQ y cadenas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edd1d-117">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- [<span data-ttu-id="edd1d-118">LINQ y directorios de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edd1d-118">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
- [<span data-ttu-id="edd1d-119">Cómo: generar XML a partir de archivos CSV</span><span class="sxs-lookup"><span data-stu-id="edd1d-119">How to: Generate XML from CSV Files</span></span>](../../../../standard/linq/generate-xml-csv-files.md)
