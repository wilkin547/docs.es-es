---
description: 'Más información acerca de: esta aplicación de instancia única no se pudo conectar a la instancia original'
title: Esta aplicación de una sola instancia no pudo conectar con la instancia original
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
ms.openlocfilehash: 123cf2cded43c10d0f538fc12f31f4065caeb6dd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100427926"
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="91678-103">Esta aplicación de una sola instancia no pudo conectar con la instancia original</span><span class="sxs-lookup"><span data-stu-id="91678-103">This single-instance application could not connect to the original instance</span></span>

<span data-ttu-id="91678-104">Esta aplicación de una sola instancia no pudo conectar con la instancia original.</span><span class="sxs-lookup"><span data-stu-id="91678-104">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="91678-105">Algunas de las posibles causas de este problema son:</span><span class="sxs-lookup"><span data-stu-id="91678-105">Some of the possible causes for this problem are as follows:</span></span>  
  
- <span data-ttu-id="91678-106">La instancia original ha dejado de responder.</span><span class="sxs-lookup"><span data-stu-id="91678-106">The original instance stopped responding.</span></span>  
  
- <span data-ttu-id="91678-107">La aplicación no tiene permisos para crear los objetos de kernel.</span><span class="sxs-lookup"><span data-stu-id="91678-107">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="91678-108">Para obtener más información sobre los objetos de kernel, consulte [exclusiones mutuas](../../standard/threading/mutexes.md).</span><span class="sxs-lookup"><span data-stu-id="91678-108">For more information about kernel objects, see [Mutexes](../../standard/threading/mutexes.md).</span></span>  
  
     <span data-ttu-id="91678-109">El nombre base de los objetos de kernel procede de concatenar el GUID del ensamblado, el número de la versión principal y el número de la versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="91678-109">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="91678-110">Por ejemplo, el nombre base podría ser `3639f15d-9547-43da-8145-60da347829915.1`.</span><span class="sxs-lookup"><span data-stu-id="91678-110">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="91678-111">Para corregir este error al desarrollar la aplicación</span><span class="sxs-lookup"><span data-stu-id="91678-111">To correct this error when developing the application</span></span>  
  
1. <span data-ttu-id="91678-112">Compruebe que la aplicación no entra en un estado que no responde.</span><span class="sxs-lookup"><span data-stu-id="91678-112">Check that the application does not go into an unresponsive state.</span></span>  
  
2. <span data-ttu-id="91678-113">Compruebe que la aplicación tiene permisos suficientes para crear objetos de kernel.</span><span class="sxs-lookup"><span data-stu-id="91678-113">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3. <span data-ttu-id="91678-114">Reinicie la instancia original de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91678-114">Restart the original instance of the application.</span></span>  
  
4. <span data-ttu-id="91678-115">Reinicie el equipo para borrar cualquier proceso que pueda estar haciendo uso del recurso necesario para conectarse a la aplicación de instancia original.</span><span class="sxs-lookup"><span data-stu-id="91678-115">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5. <span data-ttu-id="91678-116">Anote las circunstancias en las que se produjo el error y llame a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91678-116">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91678-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91678-117">See also</span></span>

- [<span data-ttu-id="91678-118">Conceptos básicos del depurador</span><span class="sxs-lookup"><span data-stu-id="91678-118">Debugger Basics</span></span>](/visualstudio/debugger/debugger-feature-tour)
