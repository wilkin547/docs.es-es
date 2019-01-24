---
title: Procedimiento Reproducir un sonido desde Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playing sounds [Windows Forms], Windows Forms
- sounds [Windows Forms], playing
- sounds
- My.Computer.Audio object [Windows Forms], playing sounds
- examples [Windows Forms], sounds
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
ms.openlocfilehash: 02b0cb2952e11946f994819bb09a55167781137c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607256"
---
# <a name="how-to-play-a-sound-from-a-windows-form"></a><span data-ttu-id="a1254-102">Procedimiento Reproducir un sonido desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a1254-102">How to: Play a Sound from a Windows Form</span></span>
<span data-ttu-id="a1254-103">En este ejemplo se reproduce un sonido en una ruta de acceso determinada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a1254-103">This example plays a sound at a given path at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1254-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1254-104">Example</span></span>  
  
```vb  
Sub PlaySimpleSound()  
    My.Computer.Audio.Play("c:\Windows\Media\chimes.wav")  
End Sub  
```  
  
```csharp  
private void playSimpleSound()  
{  
    SoundPlayer simpleSound = new SoundPlayer(@"c:\Windows\Media\chimes.wav");  
    simpleSound.Play();  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a1254-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a1254-105">Compiling the Code</span></span>  
 <span data-ttu-id="a1254-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="a1254-106">This example requires:</span></span>  
  
-   <span data-ttu-id="a1254-107">Que reemplace el nombre de archivo `"c:\Windows\Media\chimes.wav"` por un nombre de archivo válido.</span><span class="sxs-lookup"><span data-stu-id="a1254-107">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
-   <span data-ttu-id="a1254-108">(C#) Una referencia a la <xref:System.Media?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a1254-108">(C#) A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a1254-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a1254-109">Robust Programming</span></span>  
 <span data-ttu-id="a1254-110">Las operaciones de archivo se deberían agregar dentro de los bloques de control de excepciones estructurado adecuados.</span><span class="sxs-lookup"><span data-stu-id="a1254-110">File operations should be enclosed within appropriate structured exception handling blocks.</span></span>  
  
 <span data-ttu-id="a1254-111">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="a1254-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="a1254-112">El nombre de la ruta de acceso es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="a1254-112">The path name is malformed.</span></span> <span data-ttu-id="a1254-113">Por ejemplo, contiene caracteres no válidos o solo tiene espacios en blanco (clase <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="a1254-113">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="a1254-114">La ruta de acceso es de solo lectura (clase <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="a1254-114">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="a1254-115">El nombre de la ruta de acceso es `null` (clase <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="a1254-115">The path name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="a1254-116">El nombre de la ruta de acceso es demasiado largo (clase <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="a1254-116">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="a1254-117">La ruta de acceso no es válida (clase <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="a1254-117">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="a1254-118">La ruta de acceso es solo un signo de dos puntos ":" (<xref:System.NotSupportedException> clase).</span><span class="sxs-lookup"><span data-stu-id="a1254-118">The path is only a colon, ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a1254-119">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a1254-119">.NET Framework Security</span></span>  
 <span data-ttu-id="a1254-120">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="a1254-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="a1254-121">Por ejemplo, es posible que el archivo `Form1.vb` no sea un archivo de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a1254-121">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="a1254-122">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1254-122">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1254-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1254-123">See also</span></span>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="a1254-124">Cómo: Cargar un sonido de forma asincrónica en un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="a1254-124">How to: Load a Sound Asynchronously within a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-load-a-sound-asynchronously-within-a-windows-form.md)

