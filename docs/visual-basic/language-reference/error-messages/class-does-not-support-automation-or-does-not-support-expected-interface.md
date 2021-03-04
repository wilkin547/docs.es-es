---
description: 'Más información acerca de: la clase no admite Automation o no admite la interfaz esperada'
title: Esta clase no admite automatización o no admite la interfaz esperada
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: c173eeddf3a34d6af169b91066199ce7d03cf4ba
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106636"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="29994-103">Esta clase no admite automatización o no admite la interfaz esperada</span><span class="sxs-lookup"><span data-stu-id="29994-103">Class does not support Automation or does not support expected interface</span></span>

<span data-ttu-id="29994-104">La clase especificada en la llamada a la función `GetObject` o a la función `CreateObject` no ha expuesto una interfaz de programación, o bien el proyecto se ha cambiado de .dll a .exe (o a la inversa).</span><span class="sxs-lookup"><span data-stu-id="29994-104">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="29994-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="29994-105">To correct this error</span></span>  
  
1. <span data-ttu-id="29994-106">Consulte la documentación de la aplicación que creó el objeto para conocer las limitaciones en cuanto al uso de la automatización con esta clase de objeto.</span><span class="sxs-lookup"><span data-stu-id="29994-106">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2. <span data-ttu-id="29994-107">Si cambió un proyecto de .dll a .exe o a la inversa, deberá eliminar manualmente el registro del antiguo .dll o .exe.</span><span class="sxs-lookup"><span data-stu-id="29994-107">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29994-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29994-108">See also</span></span>

- [<span data-ttu-id="29994-109">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="29994-109">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="29994-110">Opciones de comentarios de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="29994-110">Visual Studio feedback options</span></span>](/visualstudio/ide/feedback-options)
