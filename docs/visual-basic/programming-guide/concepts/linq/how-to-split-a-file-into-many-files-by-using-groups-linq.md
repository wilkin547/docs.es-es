---
description: 'Más información acerca de cómo: dividir un archivo en varios archivos mediante el uso de grupos (LINQ) (Visual Basic)'
title: Procedimiento para dividir un archivo en varios mediante el uso de grupos (LINQ)
ms.date: 07/20/2015
ms.assetid: 5e8b2a2b-0b1d-4933-8a2b-03e91dfaf77f
ms.openlocfilehash: 545b572e6cd2414823a46db9c757a1876b56a5a5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100465631"
---
# <a name="how-to-split-a-file-into-many-files-by-using-groups-linq-visual-basic"></a><span data-ttu-id="430cf-103">Cómo: dividir un archivo en varios archivos mediante el uso de grupos (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="430cf-103">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="430cf-104">En este ejemplo se muestra una manera de combinar el contenido de dos archivos y luego crear un conjunto de archivos nuevos que organicen los datos de una forma nueva.</span><span class="sxs-lookup"><span data-stu-id="430cf-104">This example shows one way to merge the contents of two files and then create a set of new files that organize the data in a new way.</span></span>

### <a name="to-create-the-data-files"></a><span data-ttu-id="430cf-105">Para crear los archivos de datos</span><span class="sxs-lookup"><span data-stu-id="430cf-105">To create the data files</span></span>

1. <span data-ttu-id="430cf-106">Copie estos nombres en un archivo de texto denominado names1.txt y guárdelo en la carpeta del proyecto:</span><span class="sxs-lookup"><span data-stu-id="430cf-106">Copy these names into a text file that is named names1.txt and save it in your project folder:</span></span>

    ```text
    Bankov, Peter
    Holm, Michael
    Garcia, Hugo
    Potra, Cristina
    Noriega, Fabricio
    Aw, Kam Foo
    Beebe, Ann
    Toyoshima, Tim
    Guy, Wey Yuan
    Garcia, Debra
    ```

2. <span data-ttu-id="430cf-107">Copie estos nombres en un archivo de texto denominado names2.txt y guárdelo en la carpeta del proyecto: tenga en cuenta que los dos archivos tienen algunos nombres en común.</span><span class="sxs-lookup"><span data-stu-id="430cf-107">Copy these names into a text file that is named names2.txt and save it in your project folder: Note that the two files have some names in common.</span></span>

    ```text
    Liu, Jinghao
    Bankov, Peter
    Holm, Michael
    Garcia, Hugo
    Beebe, Ann
    Gilchrist, Beth
    Myrcha, Jacek
    Giakoumakis, Leo
    McLin, Nkenge
    El Yassir, Mehdi
    ```

## <a name="example"></a><span data-ttu-id="430cf-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="430cf-108">Example</span></span>

```vb
Class SplitWithGroups

    Shared Sub Main()

        Dim fileA As String() = System.IO.File.ReadAllLines("../../../names1.txt")
        Dim fileB As String() = System.IO.File.ReadAllLines("../../../names2.txt")

        ' Concatenate and remove duplicate names based on
        Dim mergeQuery As IEnumerable(Of String) = fileA.Union(fileB)

        ' Group the names by the first letter in the last name
        Dim groupQuery = From name In mergeQuery
                     Let n = name.Split(New Char() {","})
                     Order By n(0)
                     Group By groupKey = n(0)(0)
                     Into groupName = Group

        ' Create a new file for each group that was created
        ' Note that nested foreach loops are required to access
        ' individual items with each group.
        For Each gGroup In groupQuery
            Dim fileName As String = "..'..'..'testFile_" & gGroup.groupKey & ".txt"
            Dim sw As New System.IO.StreamWriter(fileName)
            Console.WriteLine(gGroup.groupKey)
            For Each item In gGroup.groupName
                Console.WriteLine("   " & item.name)
                sw.WriteLine(item.name)
            Next
            sw.Close()
        Next

        ' Keep console window open in debug mode.
        Console.WriteLine("Files have been written. Press any key to exit.")
        Console.ReadKey()

    End Sub
End Class
' Console Output:
' A
'    Aw, Kam Foo
' B
'    Bankov, Peter
'    Beebe, Ann
' E
'    El Yassir, Mehdi
' G
'    Garcia, Hugo
'    Garcia, Debra
'    Giakoumakis, Leo
'    Gilchrist, Beth
'    Guy, Wey Yuan
' H
'    Holm, Michael
' L
'    Liu, Jinghao
' M
'    McLin, Nkenge
'    Myrcha, Jacek
' N
'    Noriega, Fabricio
' P
'    Potra, Cristina
' T
'    Toyoshima, Tim
```

<span data-ttu-id="430cf-109">El programa escribe un archivo independiente para cada grupo en la misma carpeta que los archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="430cf-109">The program writes a separate file for each group in the same folder as the data files.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="430cf-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="430cf-110">Compile the code</span></span>

<span data-ttu-id="430cf-111">Cree un proyecto de aplicación de consola de Visual Basic, con una `Imports` instrucción para el espacio de nombres System. Linq.</span><span class="sxs-lookup"><span data-stu-id="430cf-111">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="430cf-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="430cf-112">See also</span></span>

- [<span data-ttu-id="430cf-113">LINQ y cadenas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="430cf-113">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- [<span data-ttu-id="430cf-114">LINQ y directorios de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="430cf-114">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
