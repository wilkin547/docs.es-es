---
title: "Registering Assemblies with COM | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM interop, registering assemblies"
  - "unregistering assemblies"
  - "interoperation with unmanaged code, registering assemblies"
  - "registering assemblies"
ms.assetid: 87925795-a3ae-4833-b138-125413478551
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Registering Assemblies with COM
Se puede ejecutar una herramienta de la línea de comandos, denominada [herramienta Registro de ensamblados \(Regasm.exe\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) para registrar o anular el registro de un ensamblado que se utiliza con COM.  Regasm.exe agrega información sobre la clase en el registro del sistema para que los clientes COM pueden utilizar la clase de .NET Framework transparente.  La clase <xref:System.Runtime.InteropServices.RegistrationServices> proporciona la funcionalidad equivalente.  
  
 Un componente administrado debe estar registrado en el Registro de Windows antes de que se pueda activar desde un cliente COM.  En la tabla siguiente se muestran las claves que Regasm.exe agrega normalmente al Registro de Windows.  \(000000 indica el valor real de GUID\).  
  
|GUID|Descripción|Clave del Registro|  
|----------|-----------------|------------------------|  
|CLSID|Identificador de clase|HKEY\_CLASSES\_ROOT\\CLSID\\{000…000}|  
|IID|Identificador de interfaz|HKEY\_CLASSES\_ROOT\\Interface\\{000…000}|  
|LIBID|Identificador de biblioteca|HKEY\_CLASSES\_ROOT\\TypeLib\\{000…000}|  
|Id. de programa|Identificador de programación|HKEY\_CLASSES\_ROOT\\000…000|  
  
 Bajo la clave HKCR\\CLSID\\{0000…0000}, el valor predeterminado se establece en el ProgID de la clase, y se agregan dos nuevos valores con nombre, Class y Assembly.  El motor en tiempo de ejecución lee el valor del ensamblado en el Registro y le pasa este valor al interpretador de ensamblados en tiempo de ejecución.  El interpretador de ensamblados intenta localizar el ensamblado, basándose en la información del ensamblado como el nombre y el número de versión.  Para que el interpretador de ensamblados localice un ensamblado, éste tiene que estar en una de las siguientes ubicaciones:  
  
-   La caché global de ensamblados \(debe ser un ensamblado de nombre seguro\).  
  
-   En el directorio de la aplicación.  Sólo se puede tener acceso a los ensamblados cargados desde la ruta de acceso de la aplicación desde la propia aplicación.  
  
-   Junto a una ruta de acceso especificada con la opción **\/codebase** en Regasm.exe.  
  
 Regasm.exe crea también la clave InProcServer32 bajo la clave HKCR\\CLSID\\{0000…0000}.  El valor predeterminado de la clave se establece en el nombre del archivo DLL que inicializa Common Language Runtime \(Mscoree.dll\).  
  
## Examinar entradas del Registro  
 La interoperabilidad COM proporciona una implementación de generador de clases estándar para crear una instancia de cualquier clase de .NET Framework.  Los clientes pueden llamar a **DllGetClassObject** en el archivo DLL administrado para obtener un generador de clases y crear objetos, del mismo modo que lo harían con cualquier otro componente COM.  
  
 Para la subclave de `InprocServer32`, aparece una referencia a Mscoree.dll en lugar de la biblioteca de tipos COM tradicional para indicar que Common Language Runtime crea el objeto administrado.  
  
## Vea también  
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [How to: Reference .NET Types from COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)   
 [Calling a .NET Object](http://msdn.microsoft.com/es-es/40c9626c-aea6-4bad-b8f0-c1de462efd33)   
 [Deploying an Application for COM Access](http://msdn.microsoft.com/es-es/fb63564c-c1b9-4655-a094-a235625882ce)