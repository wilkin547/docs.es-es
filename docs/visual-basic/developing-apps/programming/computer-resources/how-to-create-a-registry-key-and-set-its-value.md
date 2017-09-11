---
title: "Cómo: Crear una clave del Registro y establecer su valor en Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- RegistryKey.CreateSubKey
- RegistryKey.SetValue
dev_langs:
- VB
helpviewer_keywords:
- registry keys, creating
- registry, adding values
- registry, adding keys
- registry keys, setting values
- examples [Visual Basic], registry
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
caps.latest.revision: 30
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
ms.openlocfilehash: 106a98a1b15c37eb2cac05e1a681bf7dfed3543d
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-registry-key-and-set-its-value-in-visual-basic"></a><span data-ttu-id="77a44-102">Cómo: Crear una clave del Registro y establecer su valor en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="77a44-102">How to: Create a Registry Key and Set Its Value in Visual Basic</span></span>
<span data-ttu-id="77a44-103">El método `CreateSubKey` del objeto `My.Computer.Registry` se puede usar para crear una clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="77a44-103">The `CreateSubKey` method of the `My.Computer.Registry` object can be used to create a registry key.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="77a44-104">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="77a44-104">Procedure</span></span>  
  
#### <a name="to-create-a-registry-key"></a><span data-ttu-id="77a44-105">Para crear una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="77a44-105">To create a registry key</span></span>  
  
-   <span data-ttu-id="77a44-106">Use el método `CreateSubKey`, especificando en qué subárbol se va a colocar la clave, así como el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="77a44-106">Use the `CreateSubKey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="77a44-107">El parámetro `Subkey` no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="77a44-107">The parameter `Subkey` is not case-sensitive.</span></span> <span data-ttu-id="77a44-108">En este ejemplo se crea la clave del Registro `MyTestKey` en HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="77a44-108">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>  
  
     <span data-ttu-id="77a44-109">[!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="77a44-109">[!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]</span></span>  
  
#### <a name="to-create-a-registry-key-and-set-a-value-in-it"></a><span data-ttu-id="77a44-110">Para crear una clave del Registro y establecer un valor en él</span><span class="sxs-lookup"><span data-stu-id="77a44-110">To create a registry key and set a value in it</span></span>  
  
1.  <span data-ttu-id="77a44-111">Use el método `CreateSubkey`, especificando en qué subárbol se va a colocar la clave, así como el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="77a44-111">Use the `CreateSubkey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="77a44-112">En este ejemplo se crea la clave del Registro `MyTestKey` en HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="77a44-112">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>  
  
     <span data-ttu-id="77a44-113">[!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="77a44-113">[!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]</span></span>  
  
2.  <span data-ttu-id="77a44-114">Establezca el valor con el método `SetValue`.</span><span class="sxs-lookup"><span data-stu-id="77a44-114">Set the value with the `SetValue` method.</span></span> <span data-ttu-id="77a44-115">Este ejemplo establece el valor de la cadena.</span><span class="sxs-lookup"><span data-stu-id="77a44-115">This example sets the string value.</span></span> <span data-ttu-id="77a44-116">"MyTestKeyValue" en "This is a test value".</span><span class="sxs-lookup"><span data-stu-id="77a44-116">"MyTestKeyValue" to "This is a test value".</span></span>  
  
     <span data-ttu-id="77a44-117">[!code-vb[VbResourceTasks#14](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="77a44-117">[!code-vb[VbResourceTasks#14](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="77a44-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77a44-118">Example</span></span>  
 <span data-ttu-id="77a44-119">En este ejemplo se crea la clave del Registro `MyTestKey` en HKEY_CURRENT_USER y, después, establece el valor de la cadena `MyTestKeyValue` en `This is a test value`.</span><span class="sxs-lookup"><span data-stu-id="77a44-119">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER and then sets the string value `MyTestKeyValue` to `This is a test value`.</span></span>  
  
 <span data-ttu-id="77a44-120">[!code-vb[VbResourceTasks#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="77a44-120">[!code-vb[VbResourceTasks#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_3.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="77a44-121">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="77a44-121">Robust Programming</span></span>  
 <span data-ttu-id="77a44-122">Examine la estructura del Registro para buscar una ubicación adecuada para la clave.</span><span class="sxs-lookup"><span data-stu-id="77a44-122">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="77a44-123">Por ejemplo, puede que quiera abrir la clave HKEY_CURRENT_USER\Software del usuario actual y crear una clave con el nombre de su empresa.</span><span class="sxs-lookup"><span data-stu-id="77a44-123">For example, you may want to open the HKEY_CURRENT_USER\Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="77a44-124">Luego agregue los valores del Registro a la clave de la empresa.</span><span class="sxs-lookup"><span data-stu-id="77a44-124">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="77a44-125">Cuando se esté leyendo el Registro desde una aplicación Web, el usuario actual dependerá de la autenticación y suplantación implementadas en la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="77a44-125">When reading the registry from a Web application, the current user depends on the authentication and impersonation implemented in the Web application.</span></span>  
  
 <span data-ttu-id="77a44-126">Es más seguro escribir datos en la carpeta de usuario (<xref:Microsoft.Win32.Registry.CurrentUser>) que en el equipo local (<xref:Microsoft.Win32.Registry.LocalMachine>).</span><span class="sxs-lookup"><span data-stu-id="77a44-126">It is more secure to write data to the user folder (<xref:Microsoft.Win32.Registry.CurrentUser>) rather than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span>  
  
 <span data-ttu-id="77a44-127">Cuando se crea un valor del Registro, se debe decidir qué hacer si ese valor ya existe.</span><span class="sxs-lookup"><span data-stu-id="77a44-127">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="77a44-128">Puede que otro proceso, quizás uno malintencionado, ya haya creado el valor y tenga acceso a él.</span><span class="sxs-lookup"><span data-stu-id="77a44-128">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="77a44-129">Al colocar datos en el valor del Registro, estos están a disposición del otro proceso.</span><span class="sxs-lookup"><span data-stu-id="77a44-129">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="77a44-130">Para evitar esto, use el método <xref:Microsoft.Win32.RegistryKey.GetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="77a44-130">To prevent this, use the <xref:Microsoft.Win32.RegistryKey.GetValue%2A> method.</span></span> <span data-ttu-id="77a44-131">Devuelve `Nothing` si la clave ya no existe.</span><span class="sxs-lookup"><span data-stu-id="77a44-131">It returns `Nothing` if the key does not already exist.</span></span>  
  
 <span data-ttu-id="77a44-132">Aunque la clave del Registro esté protegida por listas de control de acceso (ACL), no es seguro almacenar en ella datos secretos (por ejemplo, contraseñas) como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="77a44-132">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (Access Control Lists).</span></span>  
  
 <span data-ttu-id="77a44-133">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="77a44-133">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="77a44-134">Que el nombre de la clave sea `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="77a44-134">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="77a44-135">Que el usuario no tenga permisos para crear claves del Registro (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="77a44-135">The user does not have permissions to create registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="77a44-136">Que el nombre de la clave supere el límite de 255 caracteres (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="77a44-136">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="77a44-137">Que la clave esté cerrada (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="77a44-137">The key is closed (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="77a44-138">Que la clave del Registro sea de solo lectura (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="77a44-138">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="77a44-139">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="77a44-139">.NET Framework Security</span></span>  
 <span data-ttu-id="77a44-140">Para ejecutar este proceso, el ensamblado necesita un nivel de privilegio concedido por la clase <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="77a44-140">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="77a44-141">Si ejecuta el proceso en un contexto de confianza parcial, este podría desencadenar una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="77a44-141">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="77a44-142">De igual manera, el usuario debe tener las ACL correctas para crear o escribir en la configuración.</span><span class="sxs-lookup"><span data-stu-id="77a44-142">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="77a44-143">Por ejemplo, una aplicación local que tenga permiso de seguridad de acceso del código puede que no tenga permiso para el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="77a44-143">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="77a44-144">Para obtener más información, vea [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="77a44-144">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77a44-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="77a44-145">See Also</span></span>  
 <span data-ttu-id="77a44-146"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span><span class="sxs-lookup"><span data-stu-id="77a44-146"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span></span>   
 <span data-ttu-id="77a44-147"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A></span><span class="sxs-lookup"><span data-stu-id="77a44-147"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A></span></span>   
 <span data-ttu-id="77a44-148"><xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A></span><span class="sxs-lookup"><span data-stu-id="77a44-148"><xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A></span></span>   
 <span data-ttu-id="77a44-149">[Leer y escribir en el Registro](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="77a44-149">[Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span></span>  
 <span data-ttu-id="77a44-150">[Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8) (Conceptos básicos sobre la seguridad de acceso del código)</span><span class="sxs-lookup"><span data-stu-id="77a44-150">[Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8)</span></span>

