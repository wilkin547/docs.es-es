---
title: Leer y escribir en el Registro (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a207b169e267fbcaccd46f7240d81afb3db27a8c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a><span data-ttu-id="9468a-102">Leer y escribir en el Registro (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9468a-102">Reading from and Writing to the Registry (Visual Basic)</span></span>
<span data-ttu-id="9468a-103">En este tema se describen las tareas y los temas conceptuales asociados al Registro.</span><span class="sxs-lookup"><span data-stu-id="9468a-103">This topic describes task and conceptual topics that are associated with the registry.</span></span>  
  
 <span data-ttu-id="9468a-104">Al programar en Visual Basic, puede optar por acceder al Registro mediante las funciones proporcionadas por Visual Basic o mediante las clases del Registro de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9468a-104">When programming in Visual Basic, you can choose to access the registry by means of either the functions provided by Visual Basic or the registry classes of the .NET Framework.</span></span> <span data-ttu-id="9468a-105">El Registro hospeda información del sistema operativo, así como de las aplicaciones hospedadas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9468a-105">The registry hosts information from the operating system as well as information from applications hosted on the machine.</span></span> <span data-ttu-id="9468a-106">Si trabaja con el Registro, puede poner en peligro la seguridad al permitir accesos inadecuados a recursos del sistema o a información protegida.</span><span class="sxs-lookup"><span data-stu-id="9468a-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9468a-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9468a-107">In This Section</span></span>  
 [<span data-ttu-id="9468a-108">Crear una clave del Registro y establecer su valor</span><span class="sxs-lookup"><span data-stu-id="9468a-108">How to: Create a Registry Key and Set Its Value</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 <span data-ttu-id="9468a-109">Describe cómo usar los métodos `CreateSubKey` y `SetValue` del objeto `My.Computer.Registry` para crear una clave del Registro y establecer su valor.</span><span class="sxs-lookup"><span data-stu-id="9468a-109">Describes how to use the `CreateSubKey` and `SetValue` methods of the `My.Computer.Registry` object to create a registry key and set its value.</span></span>  
  
 [<span data-ttu-id="9468a-110">Leer un valor a partir de una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="9468a-110">How to: Read a Value from a Registry Key</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 <span data-ttu-id="9468a-111">Describe cómo usar el método `GetValue` del objeto `My.Computer.Registry` para leer un valor de una clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="9468a-111">Describes how to use the `GetValue` method of the `My.Computer.Registry` object to read a value from a registry key.</span></span>  
  
 [<span data-ttu-id="9468a-112">Eliminar una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="9468a-112">How to: Delete a Registry Key</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 <span data-ttu-id="9468a-113">Describe cómo usar el método `DeleteSubKey` de la propiedad `My.Computer.Registry.CurrentUser` para eliminar una clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="9468a-113">Describes how to use the `DeleteSubKey` method of the `My.Computer.Registry.CurrentUser` property to delete a registry key.</span></span>  
  
 [<span data-ttu-id="9468a-114">Leer y escribir en el Registro mediante Microsoft.Win32 Namespace</span><span class="sxs-lookup"><span data-stu-id="9468a-114">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 <span data-ttu-id="9468a-115">Describe cómo usar las clases `Registry` y `RegistryKey` de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] para tener acceso al Registro.</span><span class="sxs-lookup"><span data-stu-id="9468a-115">Describes how to use the `Registry` and `RegistryKey` classes of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to access the registry.</span></span>  
  
 [<span data-ttu-id="9468a-116">Seguridad y Registro</span><span class="sxs-lookup"><span data-stu-id="9468a-116">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 <span data-ttu-id="9468a-117">Describe problemas de seguridad que afectan al Registro.</span><span class="sxs-lookup"><span data-stu-id="9468a-117">Discusses security issues involving the registry.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9468a-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="9468a-118">Related Sections</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 <span data-ttu-id="9468a-119">Enumera y explica los miembros del objeto `My.Computer.Registry`.</span><span class="sxs-lookup"><span data-stu-id="9468a-119">Lists and explains members of the `My.Computer.Registry` object.</span></span>  
  
 <xref:Microsoft.Win32.Registry>  
 <span data-ttu-id="9468a-120">Ofrece información general sobre la clase `Registry`, junto con vínculos a claves y miembros individuales.</span><span class="sxs-lookup"><span data-stu-id="9468a-120">Presents an overview of the `Registry` class, along with links to individual keys and members.</span></span>
