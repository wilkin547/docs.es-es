---
title: "Cómo: Crear archivos o carpetas (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 150190eeef829bd0431eeea7789025b9905553e3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a><span data-ttu-id="396b6-102">Cómo: Crear archivos o carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="396b6-102">How to: Create a File or Folder (C# Programming Guide)</span></span>
<span data-ttu-id="396b6-103">Puede crear una carpeta en el equipo mediante programación, crear una subcarpeta, crear un archivo en la subcarpeta y escribir datos en el archivo.</span><span class="sxs-lookup"><span data-stu-id="396b6-103">You can programmatically create a folder on your computer, create a subfolder, create a file in the subfolder, and write data to the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="396b6-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="396b6-104">Example</span></span>  
 <span data-ttu-id="396b6-105">[!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="396b6-105">[!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]</span></span>  
  
 <span data-ttu-id="396b6-106">Si la carpeta ya existe, <xref:System.IO.Directory.CreateDirectory%2A> no efectúa ninguna acción y no se devuelve ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="396b6-106">If the folder already exists, <xref:System.IO.Directory.CreateDirectory%2A> does nothing, and no exception is thrown.</span></span> <span data-ttu-id="396b6-107">Sin embargo, <xref:System.IO.File.Create%2A?displayProperty=fullName> reemplaza un archivo existente por otro nuevo.</span><span class="sxs-lookup"><span data-stu-id="396b6-107">However, <xref:System.IO.File.Create%2A?displayProperty=fullName> replaces an existing file with a new file.</span></span> <span data-ttu-id="396b6-108">En el ejemplo se usa una instrucción `if`-`else` para evitar que se sustituya un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="396b6-108">The example uses an `if`-`else` statement to prevent an existing file from being replaced.</span></span>  
  
 <span data-ttu-id="396b6-109">Al realizar los siguientes cambios en el ejemplo, puede especificar diferentes resultados en función de si ya existe un archivo con un nombre determinado.</span><span class="sxs-lookup"><span data-stu-id="396b6-109">By making the following changes in the example, you can specify different outcomes based on whether a file with a certain name already exists.</span></span> <span data-ttu-id="396b6-110">Si no existe ese archivo, el código crea uno.</span><span class="sxs-lookup"><span data-stu-id="396b6-110">If such a file doesn't exist, the code creates one.</span></span> <span data-ttu-id="396b6-111">Si ese archivo ya existe, el código anexa datos a ese archivo.</span><span class="sxs-lookup"><span data-stu-id="396b6-111">If such a file exists, the code appends data to that file.</span></span>  
  
-   <span data-ttu-id="396b6-112">Especifique un nombre de archivo no aleatorio.</span><span class="sxs-lookup"><span data-stu-id="396b6-112">Specify a non-random file name.</span></span>  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
-   <span data-ttu-id="396b6-113">Sustituya la instrucción `if`-`else` por la instrucción `using` en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="396b6-113">Replace the `if`-`else` statement with the `using` statement in the following code.</span></span>  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 <span data-ttu-id="396b6-114">Ejecute el ejemplo varias veces para comprobar que los datos se agreguen al archivo cada vez.</span><span class="sxs-lookup"><span data-stu-id="396b6-114">Run the example several times to verify that data is added to the file each time.</span></span>  
  
 <span data-ttu-id="396b6-115">Para obtener más valores `FileMode` que puede probar, consulte <xref:System.IO.FileMode>.</span><span class="sxs-lookup"><span data-stu-id="396b6-115">For more `FileMode` values that you can try, see <xref:System.IO.FileMode>.</span></span>  
  
 <span data-ttu-id="396b6-116">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="396b6-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="396b6-117">El nombre de la carpeta tiene un formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="396b6-117">The folder name is malformed.</span></span> <span data-ttu-id="396b6-118">Por ejemplo, contiene caracteres no válidos o solo tiene espacios en blanco (clase <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="396b6-118">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span> <span data-ttu-id="396b6-119">Use la clase <xref:System.IO.Path> para crear nombres de ruta válidos.</span><span class="sxs-lookup"><span data-stu-id="396b6-119">Use the <xref:System.IO.Path> class to create valid path names.</span></span>  
  
-   <span data-ttu-id="396b6-120">La carpeta principal de la que se va a crear es de solo lectura (clase <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="396b6-120">The parent folder of the folder to be created is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="396b6-121">El nombre de la carpeta es `null` (clase <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="396b6-121">The folder name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="396b6-122">El nombre de la carpeta es demasiado largo (clase <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="396b6-122">The folder name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="396b6-123">El nombre de la carpeta es solo un carácter de dos puntos, ":" (clase <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="396b6-123">The folder name is only a colon, ":" (<xref:System.IO.PathTooLongException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="396b6-124">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="396b6-124">.NET Framework Security</span></span>  
 <span data-ttu-id="396b6-125">En los casos de confiabilidad parcial, es posible que se devuelva una instancia de la clase <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="396b6-125">An instance of the <xref:System.Security.SecurityException> class may be thrown in partial-trust situations.</span></span>  
  
 <span data-ttu-id="396b6-126">Si no tiene permiso para crear la carpeta, el ejemplo devuelve una instancia de la clase <xref:System.UnauthorizedAccessException>.</span><span class="sxs-lookup"><span data-stu-id="396b6-126">If you don’t have permission to create the folder, the example throws an instance of the <xref:System.UnauthorizedAccessException> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="396b6-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="396b6-127">See Also</span></span>  
 <span data-ttu-id="396b6-128"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="396b6-128"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="396b6-129">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="396b6-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="396b6-130">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="396b6-130">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

