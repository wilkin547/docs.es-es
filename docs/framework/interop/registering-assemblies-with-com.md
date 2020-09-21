---
title: Registrar ensamblados con COM
description: Registre o anule el registro de ensamblados con COM mediante la herramienta de registro de ensamblados (Regasm.exe), que agrega información sobre la clase al registro del sistema.
ms.date: 03/30/2017
helpviewer_keywords:
- COM interop, registering assemblies
- unregistering assemblies
- interoperation with unmanaged code, registering assemblies
- registering assemblies
ms.assetid: 87925795-a3ae-4833-b138-125413478551
ms.openlocfilehash: 0adae4db393c4c01620ea896c4451c3279272fca
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559283"
---
# <a name="registering-assemblies-with-com"></a>Registrar ensamblados con COM
Puede ejecutar una herramienta de línea de comandos denominada [Registro de ensamblados (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) para registrar un ensamblado o anular su registro para su uso con COM. Regasm.exe agrega información sobre la clase al Registro del sistema, de modo que los clientes COM puedan usar la clase .NET Framework de forma transparente. La clase <xref:System.Runtime.InteropServices.RegistrationServices> proporciona la funcionalidad equivalente.  
  
 Para poder activar un componente administrado desde un cliente COM, es necesario registrarlo primero en el Registro de Windows. En la tabla siguiente se muestran las claves que Regasm.exe suele agregar al Registro de Windows. (000000 indica el valor real de GUID).  
  
|GUID|Descripción|Clave del Registro|  
|----------|-----------------|------------------|  
|CLSID|Identificador de clase|HKEY_CLASSES_ROOT\CLSID\\{000…000}|  
|IID|Identificador de interfaz|HKEY_CLASSES_ROOT\Interface\\{000…000}|  
|LIBID|Identificador de biblioteca|HKEY_CLASSES_ROOT\TypeLib\\{000…000}|  
|Id. de programa|Identificador de programación|HKEY_CLASSES_ROOT\000…000|  
  
 Bajo la clave HKCR\CLSID\\{0000…0000}, el valor predeterminado se establece en el ProgID de la clase y se agregan dos nuevos valores con nombre, Class y Assembly. El tiempo de ejecución lee el valor de Assembly del Registro y lo pasa a la resolución de ensamblado en tiempo de ejecución. La resolución de ensamblado intenta localizar el ensamblado en función de la información de ensamblado, como el nombre y el número de versión. Para que la resolución de ensamblado busque un ensamblado, este debe encontrarse en una de las ubicaciones siguientes:  
  
- En la caché global de ensamblados (debe ser un ensamblado con nombre seguro).  
  
- En el directorio de la aplicación. Los ensamblados cargados desde la ruta de acceso a la aplicación solo son accesibles desde la misma aplicación.  
  
- En una ruta de acceso de archivo especificada con la opción **/codebase** en Regasm.exe.  
  
 Regasm.exe también crea la clave InProcServer32 bajo la clave HKCR\CLSID\\{0000…0000}. El valor predeterminado de la clave se establece en el nombre del archivo DLL que inicializa Common Language Runtime (Mscoree.dll).  
  
## <a name="examining-registry-entries"></a>Examinar las entradas del Registro  
 La interoperabilidad COM proporciona una implementación de generador de clases estándar para crear una instancia de cualquier clase de .NET Framework. Los clientes pueden llamar a **DllGetClassObject** en el archivo DLL administrado para obtener un generador de clases y crear objetos, tal como harían con cualquier otro componente COM.  
  
 Para la subclave `InprocServer32`, aparece una referencia a Mscoree.dll en lugar de una biblioteca de tipos COM tradicional para indicar que Common Language Runtime crea el objeto administrado.  
  
## <a name="see-also"></a>Vea también

- [Exponer componentes de .NET Framework en COM](exposing-dotnet-components-to-com.md)
- [Cómo: Hacer referencia a tipos de .NET desde COM](how-to-reference-net-types-from-com.md)
- [Llamada a un objeto de .NET](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))
- [Implementar una aplicación para obtener acceso a COM](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))
