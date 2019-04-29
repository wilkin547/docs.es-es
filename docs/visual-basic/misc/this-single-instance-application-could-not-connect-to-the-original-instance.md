---
title: Esta aplicación de una sola instancia no pudo conectar con la instancia original
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
ms.openlocfilehash: 7ffa9b185e16cfdf8223ce84e77d1a0e1fa67f65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942619"
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="dc7ef-102">Esta aplicación de una sola instancia no pudo conectar con la instancia original</span><span class="sxs-lookup"><span data-stu-id="dc7ef-102">This single-instance application could not connect to the original instance</span></span>
<span data-ttu-id="dc7ef-103">Esta aplicación de una sola instancia no pudo conectar con la instancia original.</span><span class="sxs-lookup"><span data-stu-id="dc7ef-103">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="dc7ef-104">Algunas de las posibles causas de este problema son:</span><span class="sxs-lookup"><span data-stu-id="dc7ef-104">Some of the possible causes for this problem are as follows:</span></span>  
  
- <span data-ttu-id="dc7ef-105">La instancia original ha dejado de responder.</span><span class="sxs-lookup"><span data-stu-id="dc7ef-105">The original instance stopped responding.</span></span>  
  
- <span data-ttu-id="dc7ef-106">La aplicación no tiene permisos para crear los objetos de kernel.</span><span class="sxs-lookup"><span data-stu-id="dc7ef-106">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="dc7ef-107">Para obtener más información acerca de los objetos de kernel, vea [exclusiones mutuas](../../standard/threading/mutexes.md).</span><span class="sxs-lookup"><span data-stu-id="dc7ef-107">For more information about kernel objects, see [Mutexes](../../standard/threading/mutexes.md).</span></span>  
  
     <span data-ttu-id="dc7ef-108">El nombre base de los objetos de kernel procede de concatenar el GUID del ensamblado, el número de la versión principal y el número de la versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="dc7ef-108">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="dc7ef-109">Por ejemplo, el nombre base podría ser `3639f15d-9547-43da-8145-60da347829915.1`.</span><span class="sxs-lookup"><span data-stu-id="dc7ef-109">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="dc7ef-110">Para corregir este error al desarrollar la aplicación</span><span class="sxs-lookup"><span data-stu-id="dc7ef-110">To correct this error when developing the application</span></span>  
  
1. <span data-ttu-id="dc7ef-111">Compruebe que la aplicación no entra en un estado que no responde.</span><span class="sxs-lookup"><span data-stu-id="dc7ef-111">Check that the application does not go into an unresponsive state.</span></span>  
  
2. <span data-ttu-id="dc7ef-112">Compruebe que la aplicación tiene permisos suficientes para crear objetos de kernel.</span><span class="sxs-lookup"><span data-stu-id="dc7ef-112">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3. <span data-ttu-id="dc7ef-113">Reinicie la instancia original de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc7ef-113">Restart the original instance of the application.</span></span>  
  
4. <span data-ttu-id="dc7ef-114">Reinicie el equipo para borrar cualquier proceso que pueda estar haciendo uso del recurso necesario para conectarse a la aplicación de instancia original.</span><span class="sxs-lookup"><span data-stu-id="dc7ef-114">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5. <span data-ttu-id="dc7ef-115">Anote las circunstancias en las que se produjo el error y llame a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dc7ef-115">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc7ef-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc7ef-116">See also</span></span>

- [<span data-ttu-id="dc7ef-117">Conceptos básicos del depurador</span><span class="sxs-lookup"><span data-stu-id="dc7ef-117">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
