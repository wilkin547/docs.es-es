---
title: 'Procedimiento para crear una clave del Registro: guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: 16974db950a3a460416cfb917147439707e1d007
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635449"
---
# <a name="how-to-create-a-key-in-the-registry-c-programming-guide"></a><span data-ttu-id="88627-102">Procedimiento para crear una clave del Registro (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="88627-102">How to create a key in the registry (C# Programming Guide)</span></span>
<span data-ttu-id="88627-103">En este ejemplo se agrega el par de valores "Name" e "Isabella" al Registro del usuario actual en la clave "Names".</span><span class="sxs-lookup"><span data-stu-id="88627-103">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="88627-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88627-104">Example</span></span>  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="88627-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="88627-105">Compiling the Code</span></span>  
  
- <span data-ttu-id="88627-106">Copie el código y péguelo en el método `Main` de una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="88627-106">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
- <span data-ttu-id="88627-107">Sustituya el parámetro `Names` por el nombre de una clave que exista directamente en el nodo HKEY_CURRENT_USER del Registro.</span><span class="sxs-lookup"><span data-stu-id="88627-107">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
- <span data-ttu-id="88627-108">Sustituya el parámetro `Name` por el nombre de un valor que exista directamente en el nodo Names.</span><span class="sxs-lookup"><span data-stu-id="88627-108">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="88627-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="88627-109">Robust Programming</span></span>  
 <span data-ttu-id="88627-110">Examine la estructura del Registro para buscar una ubicación adecuada para la clave.</span><span class="sxs-lookup"><span data-stu-id="88627-110">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="88627-111">Por ejemplo, es posible que quiera abrir la clave Software del usuario actual y crear una clave con el nombre de la empresa.</span><span class="sxs-lookup"><span data-stu-id="88627-111">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="88627-112">Luego agregue los valores del Registro a la clave de la empresa.</span><span class="sxs-lookup"><span data-stu-id="88627-112">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="88627-113">Las condiciones siguientes pueden generar una excepción:</span><span class="sxs-lookup"><span data-stu-id="88627-113">The following conditions might cause an exception:</span></span>  
  
- <span data-ttu-id="88627-114">Que el nombre de la clave sea nulo.</span><span class="sxs-lookup"><span data-stu-id="88627-114">The name of the key is null.</span></span>  
  
- <span data-ttu-id="88627-115">Que el usuario no tenga permisos para crear claves del Registro.</span><span class="sxs-lookup"><span data-stu-id="88627-115">The user does not have permissions to create registry keys.</span></span>  
  
- <span data-ttu-id="88627-116">Que el nombre de la clave supere el límite de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="88627-116">The key name exceeds the 255-character limit.</span></span>  
  
- <span data-ttu-id="88627-117">Que la clave esté cerrada.</span><span class="sxs-lookup"><span data-stu-id="88627-117">The key is closed.</span></span>  
  
- <span data-ttu-id="88627-118">Que la clave del Registro sea de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="88627-118">The registry key is read-only.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="88627-119">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="88627-119">.NET Framework Security</span></span>  
 <span data-ttu-id="88627-120">Es más seguro escribir datos en la carpeta de usuario (`Microsoft.Win32.Registry.CurrentUser`) que en el equipo local (`Microsoft.Win32.Registry.LocalMachine`).</span><span class="sxs-lookup"><span data-stu-id="88627-120">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="88627-121">Cuando se crea un valor del Registro, se debe decidir qué hacer si ese valor ya existe.</span><span class="sxs-lookup"><span data-stu-id="88627-121">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="88627-122">Puede que otro proceso, quizás uno malintencionado, ya haya creado el valor y tenga acceso a él.</span><span class="sxs-lookup"><span data-stu-id="88627-122">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="88627-123">Al colocar datos en el valor del Registro, estos están a disposición del otro proceso.</span><span class="sxs-lookup"><span data-stu-id="88627-123">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="88627-124">Para evitarlo, use el método `Overload:Microsoft.Win32.RegistryKey.GetValue`</span><span class="sxs-lookup"><span data-stu-id="88627-124">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="88627-125">.</span><span class="sxs-lookup"><span data-stu-id="88627-125">method.</span></span> <span data-ttu-id="88627-126">Si la clave aún no existe, devuelve null.</span><span class="sxs-lookup"><span data-stu-id="88627-126">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="88627-127">No es seguro almacenar secretos, como contraseñas, en el Registro como texto sin formato, aunque la clave del Registro esté protegida mediante listas de control de acceso (ACL).</span><span class="sxs-lookup"><span data-stu-id="88627-127">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88627-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="88627-128">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="88627-129">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="88627-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="88627-130">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="88627-130">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="88627-131">Read, write and delete from the registry with C# (Leer, escribir y eliminar en el Registro con C#)</span><span class="sxs-lookup"><span data-stu-id="88627-131">Read, write and delete from the registry with C#</span></span>](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)
