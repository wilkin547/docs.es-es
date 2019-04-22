---
title: Procedimiento para crear un archivo en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- text files [Visual Basic], creating
- files [Visual Basic], creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
ms.openlocfilehash: a05e73a2096c82c9299e4483bbaf69e560fc2e45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839423"
---
# <a name="how-to-create-a-file-in-visual-basic"></a><span data-ttu-id="81247-102">Procedimiento para crear un archivo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="81247-102">How to: Create a File in Visual Basic</span></span>
<span data-ttu-id="81247-103">En este ejemplo se crea un archivo de texto vacío en la ruta de acceso especificada usando el método <xref:System.IO.File.Create%2A> de la clase <xref:System.IO.File>.</span><span class="sxs-lookup"><span data-stu-id="81247-103">This example creates an empty text file at the specified path using the <xref:System.IO.File.Create%2A> method in the <xref:System.IO.File> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81247-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81247-104">Example</span></span>  
 [!code-vb[VbFileIOMisc#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/class2.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="81247-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="81247-105">Compiling the Code</span></span>  
 <span data-ttu-id="81247-106">Use la variable `file` para escribir en el archivo.</span><span class="sxs-lookup"><span data-stu-id="81247-106">Use the `file` variable to write to the file.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="81247-107">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="81247-107">Robust Programming</span></span>  
 <span data-ttu-id="81247-108">Si el archivo ya existe, se reemplaza.</span><span class="sxs-lookup"><span data-stu-id="81247-108">If the file already exists, it is replaced.</span></span>  
  
 <span data-ttu-id="81247-109">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="81247-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="81247-110">El nombre de la ruta de acceso es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="81247-110">The path name is malformed.</span></span> <span data-ttu-id="81247-111">Por ejemplo, contiene caracteres no válidos o solo tiene espacios en blanco (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="81247-111">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="81247-112">La ruta de acceso es de solo lectura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="81247-112">The path is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="81247-113">El nombre de la ruta de acceso es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="81247-113">The path name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="81247-114">El nombre de la ruta de acceso es demasiado largo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="81247-114">The path name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="81247-115">La ruta de acceso no es válida (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="81247-115">The path is invalid (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="81247-116">La ruta de acceso es solo dos puntos ":" (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="81247-116">The path is only a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="81247-117">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="81247-117">.NET Framework Security</span></span>  
 <span data-ttu-id="81247-118">En entornos de confianza parcial, podría producirse una excepción <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="81247-118">A <xref:System.Security.SecurityException> may be thrown in partial-trust environments.</span></span>  
  
 <span data-ttu-id="81247-119">La llamada al método <xref:System.IO.File.Create%2A> requiere <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="81247-119">The call to the <xref:System.IO.File.Create%2A> method requires <xref:System.Security.Permissions.FileIOPermission>.</span></span>  
  
 <span data-ttu-id="81247-120">Si el usuario no tiene permisos para crear el archivo, se produce una excepción <xref:System.UnauthorizedAccessException>.</span><span class="sxs-lookup"><span data-stu-id="81247-120">An <xref:System.UnauthorizedAccessException> is thrown if the user does not have permission to create the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81247-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="81247-121">See also</span></span>

- <xref:System.IO>
- <xref:System.IO.File.Create%2A>
- [<span data-ttu-id="81247-122">Utilizar bibliotecas de código que no es de plena confianza</span><span class="sxs-lookup"><span data-stu-id="81247-122">Using Libraries from Partially Trusted Code</span></span>](../../../../framework/misc/using-libraries-from-partially-trusted-code.md)
- <span data-ttu-id="81247-123">[Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Conceptos básicos sobre la seguridad de acceso del código)</span><span class="sxs-lookup"><span data-stu-id="81247-123">[Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md)</span></span>
