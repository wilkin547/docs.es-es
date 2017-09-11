---
title: "Cómo: Eliminar una clave del Registro en Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.DeleteSetting
dev_langs:
- VB
helpviewer_keywords:
- GetSetting function
- registry, deleting values
- GetAllSettings function
- registry keys, deleting
- registry, deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0fc37aff9f6a0ae3a7953377ebf95179d01bb693
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a><span data-ttu-id="c0f59-102">Cómo: Eliminar una clave del Registro en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c0f59-102">How to: Delete a Registry Key in Visual Basic</span></span>
<span data-ttu-id="c0f59-103">Los métodos <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> y <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> se pueden usar para eliminar las claves del Registro.</span><span class="sxs-lookup"><span data-stu-id="c0f59-103">The <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> and <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> methods can be used to delete registry keys.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="c0f59-104">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="c0f59-104">Procedure</span></span>  
  
#### <a name="to-delete-a-registry-key"></a><span data-ttu-id="c0f59-105">Para eliminar una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="c0f59-105">To delete a registry key</span></span>  
  
-   <span data-ttu-id="c0f59-106">Use el método `DeleteSubKey` para eliminar una clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="c0f59-106">Use the `DeleteSubKey` method to delete a registry key.</span></span> <span data-ttu-id="c0f59-107">En este ejemplo se elimina la clave Software/TestApp en la sección CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="c0f59-107">This example deletes the key Software/TestApp in the CurrentUser hive.</span></span> <span data-ttu-id="c0f59-108">Puede cambiar esto en el código para la cadena adecuada o confiar en la información proporcionada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c0f59-108">You can change this in the code to the appropriate string, or have it rely on user-supplied information.</span></span>  
  
     <span data-ttu-id="c0f59-109">[!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0f59-109">[!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c0f59-110">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="c0f59-110">Robust Programming</span></span>  
 <span data-ttu-id="c0f59-111">El método `DeleteSubKey` devuelve una cadena vacía si el par clave/valor no existe.</span><span class="sxs-lookup"><span data-stu-id="c0f59-111">The `DeleteSubKey` method returns an empty string if the key/value pair does not exist.</span></span>  
  
 <span data-ttu-id="c0f59-112">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="c0f59-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="c0f59-113">Que el nombre de la clave sea `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="c0f59-113">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="c0f59-114">Que el usuario no tenga permisos para eliminar claves del Registro (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="c0f59-114">The user does not have permissions to delete registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="c0f59-115">Que el nombre de la clave supere el límite de 255 caracteres (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="c0f59-115">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="c0f59-116">Que la clave del Registro sea de solo lectura (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="c0f59-116">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c0f59-117">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c0f59-117">.NET Framework Security</span></span>  
 <span data-ttu-id="c0f59-118">Las llamadas del Registro producen errores si no se conceden permisos suficientes en tiempo de ejecución (<xref:System.Security.Permissions.RegistryPermission>) o si el usuario no tiene el acceso correcto (como se determina en las ACL) para crear o escribir en la configuración.</span><span class="sxs-lookup"><span data-stu-id="c0f59-118">Registry calls fail if either sufficient run-time permissions are not granted (<xref:System.Security.Permissions.RegistryPermission>) or if the user does not have the correct access (as determined by the ACLs) for creating or writing to settings.</span></span> <span data-ttu-id="c0f59-119">Por ejemplo, una aplicación local que tenga permiso de seguridad de acceso del código puede que no tenga permiso para el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c0f59-119">For example, a local application that has the code access security permission might not have operating system permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f59-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0f59-120">See Also</span></span>  
 <span data-ttu-id="c0f59-121"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span><span class="sxs-lookup"><span data-stu-id="c0f59-121"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span></span>   
 <span data-ttu-id="c0f59-122"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span><span class="sxs-lookup"><span data-stu-id="c0f59-122"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span></span>   
 <span data-ttu-id="c0f59-123"><xref:Microsoft.Win32.RegistryKey></span><span class="sxs-lookup"><span data-stu-id="c0f59-123"><xref:Microsoft.Win32.RegistryKey></span></span>   
 <span data-ttu-id="c0f59-124">[Seguridad y Registro](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="c0f59-124">[Security and the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md) </span></span>  
 [<span data-ttu-id="c0f59-125">Leer y escribir en el Registro</span><span class="sxs-lookup"><span data-stu-id="c0f59-125">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)

