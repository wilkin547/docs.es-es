---
description: 'Más información acerca de: Procedimiento: para eliminar una clave del Registro en Visual Basic'
title: Procedimiento para eliminar una clave del Registro
ms.date: 07/20/2015
f1_keywords:
- vb.DeleteSetting
helpviewer_keywords:
- GetSetting function [Visual Basic]
- registry [Visual Basic], deleting values
- GetAllSettings function
- registry keys [Visual Basic], deleting
- registry [Visual Basic], deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
ms.openlocfilehash: ca99855d30c2dd697c789bb4017429b906b3b63d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797723"
---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a><span data-ttu-id="eafdd-103">Cómo: Eliminar una clave del Registro en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eafdd-103">How to: Delete a Registry Key in Visual Basic</span></span>

<span data-ttu-id="eafdd-104">Los métodos <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> y <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> se pueden usar para eliminar las claves del Registro.</span><span class="sxs-lookup"><span data-stu-id="eafdd-104">The <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> and <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> methods can be used to delete registry keys.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="eafdd-105">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="eafdd-105">Procedure</span></span>  
  
#### <a name="to-delete-a-registry-key"></a><span data-ttu-id="eafdd-106">Para eliminar una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="eafdd-106">To delete a registry key</span></span>  
  
- <span data-ttu-id="eafdd-107">Use el método `DeleteSubKey` para eliminar una clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="eafdd-107">Use the `DeleteSubKey` method to delete a registry key.</span></span> <span data-ttu-id="eafdd-108">En este ejemplo se elimina la clave Software/TestApp en la sección CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="eafdd-108">This example deletes the key Software/TestApp in the CurrentUser hive.</span></span> <span data-ttu-id="eafdd-109">Puede cambiar esto en el código para la cadena adecuada o confiar en la información proporcionada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="eafdd-109">You can change this in the code to the appropriate string, or have it rely on user-supplied information.</span></span>  
  
     [!code-vb[VbResourceTasks#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a><span data-ttu-id="eafdd-110">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="eafdd-110">Robust Programming</span></span>  

 <span data-ttu-id="eafdd-111">El método `DeleteSubKey` devuelve una cadena vacía si el par clave/valor no existe.</span><span class="sxs-lookup"><span data-stu-id="eafdd-111">The `DeleteSubKey` method returns an empty string if the key/value pair does not exist.</span></span>  
  
 <span data-ttu-id="eafdd-112">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="eafdd-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="eafdd-113">Que el nombre de la clave sea `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="eafdd-113">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="eafdd-114">Que el usuario no tenga permisos para eliminar claves del Registro (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="eafdd-114">The user does not have permissions to delete registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="eafdd-115">Que el nombre de la clave supere el límite de 255 caracteres (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="eafdd-115">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="eafdd-116">Que la clave del Registro sea de solo lectura (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="eafdd-116">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="eafdd-117">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="eafdd-117">.NET Framework Security</span></span>  

 <span data-ttu-id="eafdd-118">Las llamadas del Registro producen errores si no se conceden permisos suficientes en tiempo de ejecución (<xref:System.Security.Permissions.RegistryPermission>) o si el usuario no tiene el acceso correcto (como se determina en las ACL) para crear o escribir en la configuración.</span><span class="sxs-lookup"><span data-stu-id="eafdd-118">Registry calls fail if either sufficient run-time permissions are not granted (<xref:System.Security.Permissions.RegistryPermission>) or if the user does not have the correct access (as determined by the ACLs) for creating or writing to settings.</span></span> <span data-ttu-id="eafdd-119">Por ejemplo, una aplicación local que tenga permiso de seguridad de acceso del código puede que no tenga permiso para el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="eafdd-119">For example, a local application that has the code access security permission might not have operating system permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eafdd-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="eafdd-120">See also</span></span>

- <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>
- <xref:Microsoft.Win32.RegistryKey>
- [<span data-ttu-id="eafdd-121">Seguridad y Registro</span><span class="sxs-lookup"><span data-stu-id="eafdd-121">Security and the Registry</span></span>](security-and-the-registry.md)
- [<span data-ttu-id="eafdd-122">Leer y escribir en el Registro</span><span class="sxs-lookup"><span data-stu-id="eafdd-122">Reading from and Writing to the Registry</span></span>](reading-from-and-writing-to-the-registry.md)
