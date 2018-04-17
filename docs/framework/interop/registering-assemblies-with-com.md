---
title: Registrar ensamblados con COM
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- COM interop, registering assemblies
- unregistering assemblies
- interoperation with unmanaged code, registering assemblies
- registering assemblies
ms.assetid: 87925795-a3ae-4833-b138-125413478551
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3beaffdc0660055dd047f449388216ccfdd312cc
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="registering-assemblies-with-com"></a><span data-ttu-id="3e939-102">Registrar ensamblados con COM</span><span class="sxs-lookup"><span data-stu-id="3e939-102">Registering Assemblies with COM</span></span>
<span data-ttu-id="3e939-103">Puede ejecutar una herramienta de línea de comandos denominada [Registro de ensamblados (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) para registrar un ensamblado o anular su registro para su uso con COM.</span><span class="sxs-lookup"><span data-stu-id="3e939-103">You can run a command-line tool called the [Assembly Registration Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) to register or unregister an assembly for use with COM.</span></span> <span data-ttu-id="3e939-104">Regasm.exe agrega información sobre la clase al Registro del sistema, de modo que los clientes COM puedan usar la clase .NET Framework de forma transparente.</span><span class="sxs-lookup"><span data-stu-id="3e939-104">Regasm.exe adds information about the class to the system registry so COM clients can use the .NET Framework class transparently.</span></span> <span data-ttu-id="3e939-105">La clase <xref:System.Runtime.InteropServices.RegistrationServices> proporciona la funcionalidad equivalente.</span><span class="sxs-lookup"><span data-stu-id="3e939-105">The <xref:System.Runtime.InteropServices.RegistrationServices> class provides the equivalent functionality.</span></span>  
  
 <span data-ttu-id="3e939-106">Para poder activar un componente administrado desde un cliente COM, es necesario registrarlo primero en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="3e939-106">A managed component must be registered in the Windows registry before it can be activated from a COM client.</span></span> <span data-ttu-id="3e939-107">En la tabla siguiente se muestran las claves que Regasm.exe suele agregar al Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="3e939-107">The following table shows the keys that Regasm.exe typically adds to the Windows registry.</span></span> <span data-ttu-id="3e939-108">(000000 indica el valor real de GUID).</span><span class="sxs-lookup"><span data-stu-id="3e939-108">(000000 indicates the actual GUID value.)</span></span>  
  
|<span data-ttu-id="3e939-109">GUID</span><span class="sxs-lookup"><span data-stu-id="3e939-109">GUID</span></span>|<span data-ttu-id="3e939-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e939-110">Description</span></span>|<span data-ttu-id="3e939-111">Clave del Registro</span><span class="sxs-lookup"><span data-stu-id="3e939-111">Registry key</span></span>|  
|----------|-----------------|------------------|  
|<span data-ttu-id="3e939-112">CLSID</span><span class="sxs-lookup"><span data-stu-id="3e939-112">CLSID</span></span>|<span data-ttu-id="3e939-113">Identificador de clase</span><span class="sxs-lookup"><span data-stu-id="3e939-113">Class identifier</span></span>|<span data-ttu-id="3e939-114">HKEY_CLASSES_ROOT\CLSID\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="3e939-114">HKEY_CLASSES_ROOT\CLSID\\{000…000}</span></span>|  
|<span data-ttu-id="3e939-115">IID</span><span class="sxs-lookup"><span data-stu-id="3e939-115">IID</span></span>|<span data-ttu-id="3e939-116">Identificador de interfaz</span><span class="sxs-lookup"><span data-stu-id="3e939-116">Interface identifier</span></span>|<span data-ttu-id="3e939-117">HKEY_CLASSES_ROOT\Interface\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="3e939-117">HKEY_CLASSES_ROOT\Interface\\{000…000}</span></span>|  
|<span data-ttu-id="3e939-118">LIBID</span><span class="sxs-lookup"><span data-stu-id="3e939-118">LIBID</span></span>|<span data-ttu-id="3e939-119">Identificador de biblioteca</span><span class="sxs-lookup"><span data-stu-id="3e939-119">Library identifier</span></span>|<span data-ttu-id="3e939-120">HKEY_CLASSES_ROOT\TypeLib\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="3e939-120">HKEY_CLASSES_ROOT\TypeLib\\{000…000}</span></span>|  
|<span data-ttu-id="3e939-121">Id. de programa</span><span class="sxs-lookup"><span data-stu-id="3e939-121">ProgID</span></span>|<span data-ttu-id="3e939-122">Identificador de programación</span><span class="sxs-lookup"><span data-stu-id="3e939-122">Programmatic identifier</span></span>|<span data-ttu-id="3e939-123">HKEY_CLASSES_ROOT\000…000</span><span class="sxs-lookup"><span data-stu-id="3e939-123">HKEY_CLASSES_ROOT\000…000</span></span>|  
  
 <span data-ttu-id="3e939-124">Bajo la clave HKCR\CLSID\\{0000…0000}, el valor predeterminado se establece en el ProgID de la clase y se agregan dos nuevos valores con nombre, Class y Assembly.</span><span class="sxs-lookup"><span data-stu-id="3e939-124">Under the HKCR\CLSID\\{0000…0000} key, the default value is set to the ProgID of the class, and two new named values, Class and Assembly, are added.</span></span> <span data-ttu-id="3e939-125">El tiempo de ejecución lee el valor de Assembly del Registro y lo pasa a la resolución de ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3e939-125">The runtime reads the Assembly value from the registry and passes it on to the runtime assembly resolver.</span></span> <span data-ttu-id="3e939-126">La resolución de ensamblado intenta localizar el ensamblado en función de la información de ensamblado, como el nombre y el número de versión.</span><span class="sxs-lookup"><span data-stu-id="3e939-126">The assembly resolver attempts to locate the assembly, based on assembly information such as the name and version number.</span></span> <span data-ttu-id="3e939-127">Para que la resolución de ensamblado busque un ensamblado, este debe encontrarse en una de las ubicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3e939-127">For the assembly resolver to locate an assembly, the assembly has to be in one of the following locations:</span></span>  
  
-   <span data-ttu-id="3e939-128">En la caché global de ensamblados (debe ser un ensamblado con nombre seguro).</span><span class="sxs-lookup"><span data-stu-id="3e939-128">The global assembly cache (must be a strong-named assembly).</span></span>  
  
-   <span data-ttu-id="3e939-129">En el directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e939-129">In the application directory.</span></span> <span data-ttu-id="3e939-130">Los ensamblados cargados desde la ruta de acceso a la aplicación solo son accesibles desde la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e939-130">Assemblies loaded from the application path are only accessible from that application.</span></span>  
  
-   <span data-ttu-id="3e939-131">En una ruta de acceso de archivo especificada con la opción **/codebase** en Regasm.exe.</span><span class="sxs-lookup"><span data-stu-id="3e939-131">Along an file path specified with the **/codebase** option to Regasm.exe.</span></span>  
  
 <span data-ttu-id="3e939-132">Regasm.exe también crea la clave InProcServer32 bajo la clave HKCR\CLSID\\{0000…0000}.</span><span class="sxs-lookup"><span data-stu-id="3e939-132">Regasm.exe also creates the InProcServer32 key under the HKCR\CLSID\\{0000…0000} key.</span></span> <span data-ttu-id="3e939-133">El valor predeterminado de la clave se establece en el nombre del archivo DLL que inicializa Common Language Runtime (Mscoree.dll).</span><span class="sxs-lookup"><span data-stu-id="3e939-133">The default value for the key is set to the name of the DLL that initializes the common language runtime (Mscoree.dll).</span></span>  
  
## <a name="examining-registry-entries"></a><span data-ttu-id="3e939-134">Examinar las entradas del Registro</span><span class="sxs-lookup"><span data-stu-id="3e939-134">Examining Registry Entries</span></span>  
 <span data-ttu-id="3e939-135">La interoperabilidad COM proporciona una implementación de generador de clases estándar para crear una instancia de cualquier clase de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3e939-135">COM interop provides a standard class factory implementation to create an instance of any .NET Framework class.</span></span> <span data-ttu-id="3e939-136">Los clientes pueden llamar a **DllGetClassObject** en el archivo DLL administrado para obtener un generador de clases y crear objetos, tal como harían con cualquier otro componente COM.</span><span class="sxs-lookup"><span data-stu-id="3e939-136">Clients can call **DllGetClassObject** on the managed DLL to get a class factory and create objects, just as they would with any other COM component.</span></span>  
  
 <span data-ttu-id="3e939-137">Para la subclave `InprocServer32`, aparece una referencia a Mscoree.dll en lugar de una biblioteca de tipos COM tradicional para indicar que Common Language Runtime crea el objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="3e939-137">For the `InprocServer32` subkey, a reference to Mscoree.dll appears in place of a traditional COM type library to indicate that the common language runtime creates the managed object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e939-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e939-138">See Also</span></span>  
 [<span data-ttu-id="3e939-139">Exponer componentes de .NET Framework en COM</span><span class="sxs-lookup"><span data-stu-id="3e939-139">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="3e939-140">Cómo: Hacer referencia a tipos de .NET desde COM</span><span class="sxs-lookup"><span data-stu-id="3e939-140">How to: Reference .NET Types from COM</span></span>](how-to-reference-net-types-from-com.md)  
 <span data-ttu-id="3e939-141">[Llamar a un objeto de .NET](https://msdn.microsoft.com/library/40c9626c-aea6-4bad-b8f0-c1de462efd33(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3e939-141">[Calling a .NET Object](https://msdn.microsoft.com/library/40c9626c-aea6-4bad-b8f0-c1de462efd33(v=vs.100))</span></span>  
 <span data-ttu-id="3e939-142">[Implementar una aplicación para obtener acceso a COM](https://msdn.microsoft.com/library/fb63564c-c1b9-4655-a094-a235625882ce(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3e939-142">[Deploying an Application for COM Access](https://msdn.microsoft.com/library/fb63564c-c1b9-4655-a094-a235625882ce(v=vs.100))</span></span>
