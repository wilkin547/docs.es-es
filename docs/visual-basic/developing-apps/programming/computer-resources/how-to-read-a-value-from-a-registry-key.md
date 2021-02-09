---
description: 'Más información acerca de: Procedimiento: para leer un valor a partir de una clave del Registro en Visual Basic'
title: Procedimiento para leer un valor en una clave del Registro
ms.date: 07/20/2015
helpviewer_keywords:
- registry keys [Visual Basic], determining if a value exists in
- My.Computer.Registry object, examples
- registry [Visual Basic], determining if values exist
- registry keys [Visual Basic], reading from
- registry [Visual Basic], reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
ms.openlocfilehash: e062e40fe1c8876864e633079fc22e2c83cfb5d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797684"
---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a><span data-ttu-id="2be61-103">Cómo: Leer un valor a partir de una clave del Registro en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2be61-103">How to: Read a Value from a Registry Key in Visual Basic</span></span>

<span data-ttu-id="2be61-104">El método `GetValue` del objeto `My.Computer.Registry` se puede usar para leer valores en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="2be61-104">The `GetValue` method of the `My.Computer.Registry` object can be used to read values in the Windows registry.</span></span>  
  
 <span data-ttu-id="2be61-105">Si la clave, "Software\MyApp" en el ejemplo siguiente, no existe, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="2be61-105">If the key, "Software\MyApp" in the following example, does not exist, an exception is thrown.</span></span> <span data-ttu-id="2be61-106">Si `ValueName`, "Nombre" en el ejemplo siguiente, no existe, se devuelve `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="2be61-106">If the `ValueName`,  "Name" in the following example, does not exist, `Nothing` is returned.</span></span>  
  
 <span data-ttu-id="2be61-107">El método `GetValue` también se puede usar para determinar si existe un valor determinado en una clave del Registro específica.</span><span class="sxs-lookup"><span data-stu-id="2be61-107">The `GetValue` method can also be used to determine whether a given value exists in a specific registry key.</span></span>  
  
 <span data-ttu-id="2be61-108">Cuando el código lee el registro de una aplicación web, la autenticación y la suplantación determinan el usuario actual que se implementa en la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="2be61-108">When code reads the registry from a Web application, the current user is determined by the authentication and impersonation that is implemented in the Web application.</span></span>  
  
### <a name="to-read-a-value-from-a-registry-key"></a><span data-ttu-id="2be61-109">Para leer un valor en una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="2be61-109">To read a value from a registry key</span></span>  
  
- <span data-ttu-id="2be61-110">Use el método `GetValue` (especificando la ruta de acceso y el nombre) para leer un valor de la clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="2be61-110">Use the `GetValue` method, specifying the path and name) to read a value from registry key.</span></span> <span data-ttu-id="2be61-111">En el ejemplo siguiente se lee el valor `Name` de `HKEY_CURRENT_USER\Software\MyApp` y lo muestra en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="2be61-111">The following example reads the value `Name` from `HKEY_CURRENT_USER\Software\MyApp` and displays it in a message box.</span></span>  
  
     [!code-vb[VbResourceTasks#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#4)]  
  
 <span data-ttu-id="2be61-112">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="2be61-112">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="2be61-113">En el selector de fragmentos de código, se encuentra en **Sistema operativo Windows > Registro**.</span><span class="sxs-lookup"><span data-stu-id="2be61-113">In the code snippet picker, it is located in **Windows Operating System > Registry**.</span></span> <span data-ttu-id="2be61-114">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="2be61-114">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a><span data-ttu-id="2be61-115">Para determinar si un valor existe en una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="2be61-115">To determine whether a value exists in a registry key</span></span>  
  
- <span data-ttu-id="2be61-116">Use el método `GetValue` para recuperar el valor.</span><span class="sxs-lookup"><span data-stu-id="2be61-116">Use the `GetValue` method to retrieve the value.</span></span> <span data-ttu-id="2be61-117">El siguiente código comprueba si el valor existe y devuelve un mensaje si no es así.</span><span class="sxs-lookup"><span data-stu-id="2be61-117">The following code checks whether the value exists and returns a message if it does not.</span></span>  
  
     [!code-vb[VbResourceTasks#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#12)]  
  
## <a name="robust-programming"></a><span data-ttu-id="2be61-118">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="2be61-118">Robust Programming</span></span>  

 <span data-ttu-id="2be61-119">El registro contiene claves de nivel superior o raíz que se usan para almacenar datos.</span><span class="sxs-lookup"><span data-stu-id="2be61-119">The registry holds top-level, or root, keys that are used to store data.</span></span> <span data-ttu-id="2be61-120">Por ejemplo, la clave raíz HKEY_LOCAL_MACHINE se usa para almacenar una configuración de nivel de equipo que usan todos los usuarios, mientras que HKEY_CURRENT_USER se usa para almacenar datos específicos de un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="2be61-120">For instance, the HKEY_LOCAL_MACHINE root key is used for storing machine-level settings used by all users, while HKEY_CURRENT_USER is used for storing data specific to an individual user.</span></span>  
  
 <span data-ttu-id="2be61-121">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="2be61-121">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="2be61-122">Que el nombre de la clave sea `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="2be61-122">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="2be61-123">Que el usuario tenga permisos para leer de las claves del Registro (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="2be61-123">The user does not have permissions to read from registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="2be61-124">Que el nombre de la clave supere el límite de 255 caracteres (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="2be61-124">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2be61-125">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2be61-125">.NET Framework Security</span></span>  

 <span data-ttu-id="2be61-126">Para ejecutar este proceso, el ensamblado necesita un nivel de privilegio concedido por la clase <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="2be61-126">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="2be61-127">Si ejecuta el proceso en un contexto de confianza parcial, este podría desencadenar una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="2be61-127">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="2be61-128">De igual manera, el usuario debe tener las ACL correctas para crear o escribir en la configuración.</span><span class="sxs-lookup"><span data-stu-id="2be61-128">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="2be61-129">Por ejemplo, una aplicación local que tenga permiso de seguridad de acceso del código puede que no tenga permiso para el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2be61-129">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="2be61-130">Para obtener más información, vea [Conceptos básicos sobre la seguridad de acceso del código](../../../../framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="2be61-130">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be61-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="2be61-131">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- <xref:Microsoft.Win32.RegistryHive>
- [<span data-ttu-id="2be61-132">Leer y escribir en el Registro</span><span class="sxs-lookup"><span data-stu-id="2be61-132">Reading from and Writing to the Registry</span></span>](reading-from-and-writing-to-the-registry.md)
