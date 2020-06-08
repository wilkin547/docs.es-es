---
title: Seguridad y Registro
ms.date: 07/20/2015
helpviewer_keywords:
- security [Visual Basic], registry
- registry [Visual Basic], security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
ms.openlocfilehash: 2eba9d177769b22de3f931bc7af4905a80e316b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359973"
---
# <a name="security-and-the-registry-visual-basic"></a><span data-ttu-id="54e0c-102">La seguridad y el Registro (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54e0c-102">Security and the Registry (Visual Basic)</span></span>

<span data-ttu-id="54e0c-103">En esta página se describen las implicaciones de seguridad relativas al almacenamiento de datos en el Registro.</span><span class="sxs-lookup"><span data-stu-id="54e0c-103">This page discusses the security implications of storing data in the registry.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="54e0c-104">Permisos</span><span class="sxs-lookup"><span data-stu-id="54e0c-104">Permissions</span></span>  

 <span data-ttu-id="54e0c-105">Aunque la clave del Registro esté protegida por listas de control de acceso (ACL), no es seguro almacenar en ella datos secretos (por ejemplo, contraseñas) como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="54e0c-105">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (access control lists).</span></span>  
  
 <span data-ttu-id="54e0c-106">Si trabaja con el Registro, puede poner en peligro la seguridad al permitir accesos inadecuados a recursos del sistema o a información protegida.</span><span class="sxs-lookup"><span data-stu-id="54e0c-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span> <span data-ttu-id="54e0c-107">Para usar estas propiedades, debe tener permisos de lectura y escritura de la enumeración <xref:System.Security.Permissions.RegistryPermissionAccess>, que controla el acceso a las variables del Registro.</span><span class="sxs-lookup"><span data-stu-id="54e0c-107">To use these properties, you must have read and write permissions from the <xref:System.Security.Permissions.RegistryPermissionAccess> enumeration, which controls access to registry variables.</span></span> <span data-ttu-id="54e0c-108">Cualquier código que se ejecute con plena confianza (bajo la directiva de seguridad predeterminada, cualquier código instalado en el disco duro local del usuario) tiene los permisos necesarios para tener acceso al Registro.</span><span class="sxs-lookup"><span data-stu-id="54e0c-108">Any code running with full trust (under the default security policy, this is any code installed on the user's local hard disk) has the necessary permissions to access the registry.</span></span> <span data-ttu-id="54e0c-109">Para obtener más información, consulte la clase <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="54e0c-109">For more information, see <xref:System.Security.Permissions.RegistryPermission> class.</span></span>  
  
 <span data-ttu-id="54e0c-110">No deben almacenarse variables de Registro en ubicaciones de memoria donde pueda obtener acceso el código sin <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="54e0c-110">Registry variables should not be stored in memory locations where code without <xref:System.Security.Permissions.RegistryPermission> can access them.</span></span> <span data-ttu-id="54e0c-111">Igualmente, al conceder permisos, conceda también los privilegios mínimos necesarios para realizar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="54e0c-111">Similarly, when granting permissions, grant the minimum privileges necessary to get the job done.</span></span>  
  
 <span data-ttu-id="54e0c-112">Los valores de acceso de permiso del Registro se definen mediante la enumeración <xref:System.Security.Permissions.RegistryPermissionAccess>.</span><span class="sxs-lookup"><span data-stu-id="54e0c-112">Registry permission access values are defined by the <xref:System.Security.Permissions.RegistryPermissionAccess> enumeration.</span></span> <span data-ttu-id="54e0c-113">En la tabla siguiente se detallan sus miembros.</span><span class="sxs-lookup"><span data-stu-id="54e0c-113">The following table details its members.</span></span>  
  
|<span data-ttu-id="54e0c-114">Valor</span><span class="sxs-lookup"><span data-stu-id="54e0c-114">Value</span></span>|<span data-ttu-id="54e0c-115">Acceso a las variables del Registro</span><span class="sxs-lookup"><span data-stu-id="54e0c-115">Access to Registry Variables</span></span>|  
|-----------|----------------------------------|  
|`AllAccess`|<span data-ttu-id="54e0c-116">Creación, lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="54e0c-116">Create, read, and write</span></span>|  
|`Create`|<span data-ttu-id="54e0c-117">Crear</span><span class="sxs-lookup"><span data-stu-id="54e0c-117">Create</span></span>|  
|`NoAccess`|<span data-ttu-id="54e0c-118">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="54e0c-118">No access</span></span>|  
|`Read`|<span data-ttu-id="54e0c-119">Lectura</span><span class="sxs-lookup"><span data-stu-id="54e0c-119">Read</span></span>|  
|`Write`|<span data-ttu-id="54e0c-120">Write</span><span class="sxs-lookup"><span data-stu-id="54e0c-120">Write</span></span>|  
  
## <a name="checking-values-in-registry-keys"></a><span data-ttu-id="54e0c-121">Comprobar valores en las claves del Registro</span><span class="sxs-lookup"><span data-stu-id="54e0c-121">Checking Values in Registry Keys</span></span>  

 <span data-ttu-id="54e0c-122">Cuando se crea un valor del Registro, se debe decidir qué hacer si ese valor ya existe.</span><span class="sxs-lookup"><span data-stu-id="54e0c-122">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="54e0c-123">Puede que otro proceso, quizás uno malintencionado, ya haya creado el valor y tenga acceso a él.</span><span class="sxs-lookup"><span data-stu-id="54e0c-123">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="54e0c-124">Al colocar datos en el valor del Registro, estos están a disposición del otro proceso.</span><span class="sxs-lookup"><span data-stu-id="54e0c-124">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="54e0c-125">Para evitar esto, use el método `GetValue`.</span><span class="sxs-lookup"><span data-stu-id="54e0c-125">To prevent this, use the `GetValue` method.</span></span> <span data-ttu-id="54e0c-126">Devuelve `Nothing` si la clave ya no existe.</span><span class="sxs-lookup"><span data-stu-id="54e0c-126">It returns `Nothing` if the key does not already exist.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="54e0c-127">Cuando se esté leyendo el Registro desde una aplicación Web, la identidad del usuario actual dependerá de la autenticación y suplantación implementadas en la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="54e0c-127">When reading the registry from a Web application, the identity of current user depends on the authentication and impersonation implemented in the Web application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e0c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="54e0c-128">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [<span data-ttu-id="54e0c-129">Leer y escribir en el Registro</span><span class="sxs-lookup"><span data-stu-id="54e0c-129">Reading from and Writing to the Registry</span></span>](reading-from-and-writing-to-the-registry.md)
