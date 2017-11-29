---
title: "Esta aplicación de una sola instancia no pudo conectar con la instancia original"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fbc8458231c36f3af9ca4de524e01e19a162ee47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="43eb5-102">Esta aplicación de una sola instancia no pudo conectar con la instancia original</span><span class="sxs-lookup"><span data-stu-id="43eb5-102">This single-instance application could not connect to the original instance</span></span>
<span data-ttu-id="43eb5-103">Esta aplicación de una sola instancia no pudo conectar con la instancia original.</span><span class="sxs-lookup"><span data-stu-id="43eb5-103">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="43eb5-104">Algunas de las posibles causas de este problema son:</span><span class="sxs-lookup"><span data-stu-id="43eb5-104">Some of the possible causes for this problem are as follows:</span></span>  
  
-   <span data-ttu-id="43eb5-105">La instancia original ha dejado de responder.</span><span class="sxs-lookup"><span data-stu-id="43eb5-105">The original instance stopped responding.</span></span>  
  
-   <span data-ttu-id="43eb5-106">La aplicación no tiene permisos para crear los objetos de kernel.</span><span class="sxs-lookup"><span data-stu-id="43eb5-106">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="43eb5-107">Para obtener más información acerca de los objetos de kernel, vea [exclusiones mutuas](../../standard/threading/mutexes.md).</span><span class="sxs-lookup"><span data-stu-id="43eb5-107">For more information about kernel objects, see [Mutexes](../../standard/threading/mutexes.md).</span></span>  
  
     <span data-ttu-id="43eb5-108">El nombre base de los objetos de kernel procede de concatenar el GUID del ensamblado, el número de la versión principal y el número de la versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="43eb5-108">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="43eb5-109">Por ejemplo, el nombre base podría ser `3639f15d-9547-43da-8145-60da347829915.1`.</span><span class="sxs-lookup"><span data-stu-id="43eb5-109">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="43eb5-110">Para corregir este error al desarrollar la aplicación</span><span class="sxs-lookup"><span data-stu-id="43eb5-110">To correct this error when developing the application</span></span>  
  
1.  <span data-ttu-id="43eb5-111">Compruebe que la aplicación no entra en un estado que no responde.</span><span class="sxs-lookup"><span data-stu-id="43eb5-111">Check that the application does not go into an unresponsive state.</span></span>  
  
2.  <span data-ttu-id="43eb5-112">Compruebe que la aplicación tiene permisos suficientes para crear objetos de kernel.</span><span class="sxs-lookup"><span data-stu-id="43eb5-112">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3.  <span data-ttu-id="43eb5-113">Reinicie la instancia original de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="43eb5-113">Restart the original instance of the application.</span></span>  
  
4.  <span data-ttu-id="43eb5-114">Reinicie el equipo para borrar cualquier proceso que pueda estar haciendo uso del recurso necesario para conectarse a la aplicación de instancia original.</span><span class="sxs-lookup"><span data-stu-id="43eb5-114">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5.  <span data-ttu-id="43eb5-115">Anote las circunstancias en las que se produjo el error y llame a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43eb5-115">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43eb5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="43eb5-116">See Also</span></span>  
 [<span data-ttu-id="43eb5-117">NIB: Cómo: especificar el comportamiento de las instancias de una aplicación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43eb5-117">NIB: How to: Specify Instancing Behavior for an Application (Visual Basic)</span></span>](http://msdn.microsoft.com/en-us/48539ad8-d960-4210-beab-ee65f6c6dc6e)  
 [<span data-ttu-id="43eb5-118">Conceptos básicos del depurador</span><span class="sxs-lookup"><span data-stu-id="43eb5-118">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)  
 [<span data-ttu-id="43eb5-119">PAVEOVER Compatibilidad de productos y accesibilidad</span><span class="sxs-lookup"><span data-stu-id="43eb5-119">PAVEOVER Product Support and Accessibility</span></span>](http://msdn.microsoft.com/en-us/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)
