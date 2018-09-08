---
title: 'Cómo: determinar si un archivo es un ensamblado (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
ms.openlocfilehash: ced41279e7e192d6d5bed53dbce7378395b32e6d
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44131625"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a><span data-ttu-id="23c80-102">Cómo: determinar si un archivo es un ensamblado (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23c80-102">How to: Determine If a File Is an Assembly (Visual Basic)</span></span>
<span data-ttu-id="23c80-103">Un archivo es un ensamblado únicamente si está administrado y contiene una entrada de ensamblado en sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="23c80-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="23c80-104">Para más información sobre ensamblados y metadatos, vea el tema [Manifiesto del ensamblado](../../../../framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="23c80-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](../../../../framework/app-domains/assembly-manifest.md).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="23c80-105">Cómo determinar manualmente si un archivo es un ensamblado</span><span class="sxs-lookup"><span data-stu-id="23c80-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="23c80-106">Inicie [Ildasm.exe (el desensamblador de lenguaje intermedio)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="23c80-106">Start the [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2.  <span data-ttu-id="23c80-107">Cargue el archivo que quiere probar.</span><span class="sxs-lookup"><span data-stu-id="23c80-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="23c80-108">Si **ILDASM** notifica que el archivo no es un archivo ejecutable portable (PE), entonces no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23c80-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="23c80-109">Para obtener más información, vea el tema [Cómo: Ver el contenido de un ensamblado](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span><span class="sxs-lookup"><span data-stu-id="23c80-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="23c80-110">Cómo determinar mediante programación si un archivo es un ensamblado</span><span class="sxs-lookup"><span data-stu-id="23c80-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="23c80-111">Llame al método <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>; para ello, pase el nombre y la ruta de acceso de archivo completa del archivo que está probando.</span><span class="sxs-lookup"><span data-stu-id="23c80-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="23c80-112">Si se genera una excepción <xref:System.BadImageFormatException>, el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23c80-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23c80-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="23c80-113">Example</span></span>  
 <span data-ttu-id="23c80-114">En este ejemplo se prueba un archivo DLL para ver si es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23c80-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
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
  
 <span data-ttu-id="23c80-115">El método <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> carga el archivo de prueba y, después, lo libera cuando se lee la información.</span><span class="sxs-lookup"><span data-stu-id="23c80-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c80-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="23c80-116">See also</span></span>

- <xref:System.Reflection.AssemblyName>  
- [<span data-ttu-id="23c80-117">Conceptos de programación</span><span class="sxs-lookup"><span data-stu-id="23c80-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
- [<span data-ttu-id="23c80-118">Ensamblados y caché global de ensamblados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23c80-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](index.md)
