---
description: 'Más información acerca de: Leer y escribir en el Registro (Visual Basic)'
title: Leer y escribir en el Registro
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
ms.openlocfilehash: 0a9e32480845e617f6e4fde2f31c58eea8da4ee7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701552"
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a><span data-ttu-id="1f22b-103">Leer y escribir en el Registro (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f22b-103">Reading from and Writing to the Registry (Visual Basic)</span></span>

<span data-ttu-id="1f22b-104">En este tema se describen las tareas y los temas conceptuales asociados al Registro.</span><span class="sxs-lookup"><span data-stu-id="1f22b-104">This topic describes task and conceptual topics that are associated with the registry.</span></span>  
  
 <span data-ttu-id="1f22b-105">Al programar en Visual Basic, puede optar por acceder al registro mediante las funciones proporcionadas por Visual Basic o mediante las clases del registro de .NET.</span><span class="sxs-lookup"><span data-stu-id="1f22b-105">When programming in Visual Basic, you can choose to access the registry by means of either the functions provided by Visual Basic or the registry classes of .NET.</span></span> <span data-ttu-id="1f22b-106">El Registro hospeda información del sistema operativo, así como de las aplicaciones hospedadas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="1f22b-106">The registry hosts information from the operating system as well as information from applications hosted on the machine.</span></span> <span data-ttu-id="1f22b-107">Si trabaja con el Registro, puede poner en peligro la seguridad al permitir accesos inadecuados a recursos del sistema o a información protegida.</span><span class="sxs-lookup"><span data-stu-id="1f22b-107">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f22b-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1f22b-108">In This Section</span></span>  

 [<span data-ttu-id="1f22b-109">Crear una clave del Registro y establecer su valor</span><span class="sxs-lookup"><span data-stu-id="1f22b-109">How to: Create a Registry Key and Set Its Value</span></span>](how-to-create-a-registry-key-and-set-its-value.md)  
 <span data-ttu-id="1f22b-110">Describe cómo usar los métodos `CreateSubKey` y `SetValue` del objeto `My.Computer.Registry` para crear una clave del Registro y establecer su valor.</span><span class="sxs-lookup"><span data-stu-id="1f22b-110">Describes how to use the `CreateSubKey` and `SetValue` methods of the `My.Computer.Registry` object to create a registry key and set its value.</span></span>  
  
 [<span data-ttu-id="1f22b-111">Leer un valor a partir de una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="1f22b-111">How to: Read a Value from a Registry Key</span></span>](how-to-read-a-value-from-a-registry-key.md)  
 <span data-ttu-id="1f22b-112">Describe cómo usar el método `GetValue` del objeto `My.Computer.Registry` para leer un valor de una clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="1f22b-112">Describes how to use the `GetValue` method of the `My.Computer.Registry` object to read a value from a registry key.</span></span>  
  
 [<span data-ttu-id="1f22b-113">Eliminar una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="1f22b-113">How to: Delete a Registry Key</span></span>](how-to-delete-a-registry-key.md)  
 <span data-ttu-id="1f22b-114">Describe cómo usar el método `DeleteSubKey` de la propiedad `My.Computer.Registry.CurrentUser` para eliminar una clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="1f22b-114">Describes how to use the `DeleteSubKey` method of the `My.Computer.Registry.CurrentUser` property to delete a registry key.</span></span>  
  
 [<span data-ttu-id="1f22b-115">Leer y escribir en el Registro mediante Microsoft.Win32 Namespace</span><span class="sxs-lookup"><span data-stu-id="1f22b-115">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace</span></span>](reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 <span data-ttu-id="1f22b-116">Describe cómo usar las clases `Registry` y `RegistryKey` de .NET para acceder al registro.</span><span class="sxs-lookup"><span data-stu-id="1f22b-116">Describes how to use the `Registry` and `RegistryKey` classes of .NET to access the registry.</span></span>  
  
 [<span data-ttu-id="1f22b-117">Seguridad y Registro</span><span class="sxs-lookup"><span data-stu-id="1f22b-117">Security and the Registry</span></span>](security-and-the-registry.md)  
 <span data-ttu-id="1f22b-118">Describe problemas de seguridad que afectan al Registro.</span><span class="sxs-lookup"><span data-stu-id="1f22b-118">Discusses security issues involving the registry.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1f22b-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="1f22b-119">Related Sections</span></span>  

 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 <span data-ttu-id="1f22b-120">Enumera y explica los miembros del objeto `My.Computer.Registry`.</span><span class="sxs-lookup"><span data-stu-id="1f22b-120">Lists and explains members of the `My.Computer.Registry` object.</span></span>  
  
 <xref:Microsoft.Win32.Registry>  
 <span data-ttu-id="1f22b-121">Ofrece información general sobre la clase `Registry`, junto con vínculos a claves y miembros individuales.</span><span class="sxs-lookup"><span data-stu-id="1f22b-121">Presents an overview of the `Registry` class, along with links to individual keys and members.</span></span>
