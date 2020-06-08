---
title: Realizar tareas con My.Application, My.Computer y My.User
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 55961d6857b690fc2726f541df8a5497a3207928
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411699"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="57d41-102">Realizar tareas con My.Application, My.Computer y My.User (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57d41-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>

<span data-ttu-id="57d41-103">Los tres objetos centrales de `My` que proporcionan acceso a información y funciones de uso frecuente son `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>) y `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span><span class="sxs-lookup"><span data-stu-id="57d41-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="57d41-104">Puede usar estos objetos para acceder a información relacionada con la aplicación actual, el equipo en el que está instalada la aplicación o el usuario actual de la aplicación, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="57d41-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="57d41-105">My.Application, My.Computer y My.User</span><span class="sxs-lookup"><span data-stu-id="57d41-105">My.Application, My.Computer, and My.User</span></span>  

 <span data-ttu-id="57d41-106">En los ejemplos siguientes se muestra cómo se puede recuperar información mediante `My`.</span><span class="sxs-lookup"><span data-stu-id="57d41-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 <span data-ttu-id="57d41-107">Además de recuperar información, los miembros expuestos a través de estos tres objetos también permiten ejecutar métodos relacionados con ese objeto.</span><span class="sxs-lookup"><span data-stu-id="57d41-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="57d41-108">Por ejemplo, puede acceder a diversos métodos para manipular archivos o actualizar el registro a través de `My.Computer`.</span><span class="sxs-lookup"><span data-stu-id="57d41-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="57d41-109">La E/S de archivos es mucho más sencilla y rápida con `My`, que incluye una variedad de métodos y propiedades para manipular archivos, directorios y unidades.</span><span class="sxs-lookup"><span data-stu-id="57d41-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="57d41-110">El objeto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> permite leer archivos estructurados de gran tamaño que tienen campos delimitados o de ancho fijo.</span><span class="sxs-lookup"><span data-stu-id="57d41-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="57d41-111">En este ejemplo se abre el objeto `reader` `TextFieldParser` y se usa para leer desde `C:\TestFolder1\test1.txt`.</span><span class="sxs-lookup"><span data-stu-id="57d41-111">This example opens the `TextFieldParser` `reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 <span data-ttu-id="57d41-112">`My.Application` permite cambiar la referencia cultural de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="57d41-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="57d41-113">En el ejemplo siguiente se muestra cómo llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="57d41-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="57d41-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="57d41-114">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [<span data-ttu-id="57d41-115">Cómo My depende del tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="57d41-115">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)
