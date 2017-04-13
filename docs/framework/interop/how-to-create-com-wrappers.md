---
title: "How to: Create COM Wrappers | Microsoft Docs"
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
  - "COM,wrappers creating"
  - "COM,wrappers Visual Studio"
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Create COM Wrappers
Puede crear contenedores del Modelo de objetos componentes \(COM\) mediante las características [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] o las herramientas Tlbimp.exe y Regasm.exe de .NET Framework.  Ambos métodos generan dos tipos de contenedores COM:  
  
-   Un [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) de una biblioteca de tipos para ejecutar un objeto COM en código administrado.  
  
-   Un [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) con la configuración del Registro necesaria para ejecutar un objeto administrado en una aplicación nativa.  
  
 En [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], puede agregar el contenedor COM como una referencia a su proyecto.  
  
## Ajustar objetos COM en una aplicación administrada  
  
#### Para crear un contenedor invocable en tiempo de ejecución usando Visual Studio  
  
1.  Abra el proyecto de la aplicación administrada.  
  
2.  En el menú **Proyecto**, haga clic en **Mostrar todos los archivos**.  
  
3.  Haga clic en la opción **Agregar referencia** del menú **Proyecto**.  
  
4.  En el cuadro de diálogo Agregar referencia, haga clic en la ficha **COM**, seleccione el componente que desea utilizar y haga clic en **Aceptar**.  
  
     En el **Explorador de soluciones**, observe que el componente COM está agregado a la carpeta Referencias de su proyecto.  
  
 Ya puede escribir el código para tener acceso al objeto COM.  Puede comenzar declarando el objeto, por ejemplo, con una instrucción `Imports` para [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] o una instrucción `Using` para [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].  
  
> [!NOTE]
>  Si desea programar los componentes de Microsoft Office, instale primero los [Ensamblados de interoperabilidad primarios de Microsoft Office](http://go.microsoft.com/fwlink/?LinkId=50479) \(PIAs\) del Centro de descarga de Microsoft.  En el paso 4, seleccione la última versión de la biblioteca de objetos disponible para el producto de Office que desee, como **Microsoft Word 11.0 Object Library**.  [](http://msdn.microsoft.com/es-es/c9d2a8b9-69df-4c0b-90ca-4d85bae063c4)  
  
#### Para crear un contenedor invocable en tiempo de ejecución usando las herramientas de .NET Framework  
  
-   Ejecute la herramienta [Tlbimp.exe \(Type Library Importer\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).  
  
 Esta herramienta crea un ensamblado que contiene los metadatos en tiempo de ejecución para los tipos definidos en la biblioteca de tipos original.  
  
## Ajustar objetos administrados en una aplicación nativa  
  
#### Para crear un contenedor CCW mediante Visual Studio  
  
1.  Cree un proyecto de biblioteca de clases para la clase administrada que desea ejecutar en código nativo.  La clase debe tener un constructor predeterminado.  
  
     Compruebe que tiene un número de versión de cuatro partes completo para el ensamblado en el archivo AssemblyInfo.  Este número es necesario para mantener el control de versiones en el Registro de Windows.  Para obtener más información acerca de los números de versiones, vea [Versiones de los ensamblados](../../../docs/framework/app-domains/assembly-versioning.md).  
  
2.  En el menú **Proyecto**, haga clic en **Propiedades**.  
  
3.  Haga clic en la ficha **Compilar**.  
  
4.  Active la casilla **Registrar para interoperabilidad COM**.  
  
 Al compilar el proyecto, el ensamblado se registra automáticamente para la interoperabilidad COM.  Si está compilando una aplicación nativa en [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], puede utilizar el ensamblado haciendo clic en **Agregar referencia** en el menú **Proyecto**.  
  
#### Para crear un contenedor CCW usando las herramientas de .NET Framework  
  
-   Ejecute la herramienta [Regasm.exe \(Assembly Registration Tool\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md).  
  
 Esta herramienta lee los metadatos del ensamblado y agrega las entradas necesarias al Registro.  Como resultado, los clientes COM pueden crear de forma transparente las clases de .NET Framework.  Puede utilizar el ensamblado como si fuera una clase COM nativa.  
  
 Puede ejecutar Regasm.exe en un ensamblado situado en cualquier directorio y, a continuación, ejecutar [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para moverlo a la caché global de ensamblados.  Al mover el ensamblado, no se invalidan las entradas del Registro de la ubicación porque siempre se examina la caché global de ensamblados si no se encuentra el ensamblado en otra parte.  
  
## Vea también  
 [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md)   
 [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md)