---
title: Procedimiento para crear una clave del Registro y establecer su valor en Visual Basic
ms.date: 07/20/2015
f1_keywords:
- RegistryKey.CreateSubKey
- RegistryKey.SetValue
helpviewer_keywords:
- registry keys [Visual Basic], creating
- registry [Visual Basic], adding values
- registry [Visual Basic], adding keys
- registry keys [Visual Basic], setting values
- examples [Visual Basic], registry
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
ms.openlocfilehash: 0cadff8b44c60041e2664b1d3b70830209014301
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312624"
---
# <a name="how-to-create-a-registry-key-and-set-its-value-in-visual-basic"></a><span data-ttu-id="f3204-102">Procedimiento para crear una clave del Registro y establecer su valor en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3204-102">How to: Create a Registry Key and Set Its Value in Visual Basic</span></span>
<span data-ttu-id="f3204-103">El método `CreateSubKey` del objeto `My.Computer.Registry` se puede usar para crear una clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="f3204-103">The `CreateSubKey` method of the `My.Computer.Registry` object can be used to create a registry key.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="f3204-104">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="f3204-104">Procedure</span></span>  
  
#### <a name="to-create-a-registry-key"></a><span data-ttu-id="f3204-105">Para crear una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="f3204-105">To create a registry key</span></span>  
  
-   <span data-ttu-id="f3204-106">Use el método `CreateSubKey`, especificando en qué subárbol se va a colocar la clave, así como el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="f3204-106">Use the `CreateSubKey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="f3204-107">El parámetro `Subkey` no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f3204-107">The parameter `Subkey` is not case-sensitive.</span></span> <span data-ttu-id="f3204-108">En este ejemplo se crea la clave del Registro `MyTestKey` en HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="f3204-108">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>  
  
     [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]  
  
#### <a name="to-create-a-registry-key-and-set-a-value-in-it"></a><span data-ttu-id="f3204-109">Para crear una clave del Registro y establecer un valor en él</span><span class="sxs-lookup"><span data-stu-id="f3204-109">To create a registry key and set a value in it</span></span>  
  
1. <span data-ttu-id="f3204-110">Use el método `CreateSubkey`, especificando en qué subárbol se va a colocar la clave, así como el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="f3204-110">Use the `CreateSubkey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="f3204-111">En este ejemplo se crea la clave del Registro `MyTestKey` en HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="f3204-111">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>  
  
     [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]  
  
2. <span data-ttu-id="f3204-112">Establezca el valor con el método `SetValue`.</span><span class="sxs-lookup"><span data-stu-id="f3204-112">Set the value with the `SetValue` method.</span></span> <span data-ttu-id="f3204-113">Este ejemplo establece el valor de la cadena.</span><span class="sxs-lookup"><span data-stu-id="f3204-113">This example sets the string value.</span></span> <span data-ttu-id="f3204-114">"MyTestKeyValue" en "This is a test value".</span><span class="sxs-lookup"><span data-stu-id="f3204-114">"MyTestKeyValue" to "This is a test value".</span></span>  
  
     [!code-vb[VbResourceTasks#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="f3204-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3204-115">Example</span></span>  
 <span data-ttu-id="f3204-116">En este ejemplo se crea la clave del Registro `MyTestKey` en HKEY_CURRENT_USER y, después, establece el valor de la cadena `MyTestKeyValue` en `This is a test value`.</span><span class="sxs-lookup"><span data-stu-id="f3204-116">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER and then sets the string value `MyTestKeyValue` to `This is a test value`.</span></span>  
  
 [!code-vb[VbResourceTasks#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#15)]  
  
## <a name="robust-programming"></a><span data-ttu-id="f3204-117">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="f3204-117">Robust Programming</span></span>  
 <span data-ttu-id="f3204-118">Examine la estructura del Registro para buscar una ubicación adecuada para la clave.</span><span class="sxs-lookup"><span data-stu-id="f3204-118">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="f3204-119">Por ejemplo, puede que quiera abrir la clave HKEY_CURRENT_USER\Software del usuario actual y crear una clave con el nombre de su empresa.</span><span class="sxs-lookup"><span data-stu-id="f3204-119">For example, you may want to open the HKEY_CURRENT_USER\Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="f3204-120">Luego agregue los valores del Registro a la clave de la empresa.</span><span class="sxs-lookup"><span data-stu-id="f3204-120">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="f3204-121">Cuando se esté leyendo el Registro desde una aplicación Web, el usuario actual dependerá de la autenticación y suplantación implementadas en la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="f3204-121">When reading the registry from a Web application, the current user depends on the authentication and impersonation implemented in the Web application.</span></span>  
  
 <span data-ttu-id="f3204-122">Es más seguro escribir datos en la carpeta de usuario (<xref:Microsoft.Win32.Registry.CurrentUser>) que en el equipo local (<xref:Microsoft.Win32.Registry.LocalMachine>).</span><span class="sxs-lookup"><span data-stu-id="f3204-122">It is more secure to write data to the user folder (<xref:Microsoft.Win32.Registry.CurrentUser>) rather than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span>  
  
 <span data-ttu-id="f3204-123">Cuando se crea un valor del Registro, se debe decidir qué hacer si ese valor ya existe.</span><span class="sxs-lookup"><span data-stu-id="f3204-123">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="f3204-124">Puede que otro proceso, quizás uno malintencionado, ya haya creado el valor y tenga acceso a él.</span><span class="sxs-lookup"><span data-stu-id="f3204-124">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="f3204-125">Al colocar datos en el valor del Registro, estos están a disposición del otro proceso.</span><span class="sxs-lookup"><span data-stu-id="f3204-125">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="f3204-126">Para evitar esto, use el método <xref:Microsoft.Win32.RegistryKey.GetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3204-126">To prevent this, use the <xref:Microsoft.Win32.RegistryKey.GetValue%2A> method.</span></span> <span data-ttu-id="f3204-127">Devuelve `Nothing` si la clave ya no existe.</span><span class="sxs-lookup"><span data-stu-id="f3204-127">It returns `Nothing` if the key does not already exist.</span></span>  
  
 <span data-ttu-id="f3204-128">Aunque la clave del Registro esté protegida por listas de control de acceso (ACL), no es seguro almacenar en ella datos secretos (por ejemplo, contraseñas) como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="f3204-128">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (Access Control Lists).</span></span>  
  
 <span data-ttu-id="f3204-129">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="f3204-129">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="f3204-130">Que el nombre de la clave sea `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="f3204-130">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="f3204-131">Que el usuario no tenga permisos para crear claves del Registro (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="f3204-131">The user does not have permissions to create registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="f3204-132">Que el nombre de la clave supere el límite de 255 caracteres (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="f3204-132">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="f3204-133">Que la clave esté cerrada (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="f3204-133">The key is closed (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="f3204-134">Que la clave del Registro sea de solo lectura (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="f3204-134">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f3204-135">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f3204-135">.NET Framework Security</span></span>  
 <span data-ttu-id="f3204-136">Para ejecutar este proceso, el ensamblado necesita un nivel de privilegio concedido por la clase <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="f3204-136">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="f3204-137">Si ejecuta el proceso en un contexto de confianza parcial, este podría desencadenar una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="f3204-137">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="f3204-138">De igual manera, el usuario debe tener las ACL correctas para crear o escribir en la configuración.</span><span class="sxs-lookup"><span data-stu-id="f3204-138">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="f3204-139">Por ejemplo, una aplicación local que tenga permiso de seguridad de acceso del código puede que no tenga permiso para el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f3204-139">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="f3204-140">Para obtener más información, vea [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="f3204-140">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3204-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3204-141">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A>
- <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>
- [<span data-ttu-id="f3204-142">Leer y escribir en el Registro</span><span class="sxs-lookup"><span data-stu-id="f3204-142">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
- <span data-ttu-id="f3204-143">[Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Conceptos básicos sobre la seguridad de acceso del código)</span><span class="sxs-lookup"><span data-stu-id="f3204-143">[Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md)</span></span>
