---
title: "C&#243;mo: Crear un par de claves privada y p&#250;blica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "pares de claves para ensamblados con nombre seguro"
  - "firmar ensamblados"
  - "ensamblados [.NET Framework], firmar"
  - "pares de claves criptográficas"
  - "snk (archivos de par de claves)"
  - "pares de claves pública y privada"
  - "archivos .snk"
  - "ensamblados con nombre seguro, pares de claves"
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Crear un par de claves privada y p&#250;blica
Para firmar un ensamblado con un nombre seguro, es necesario tener un par de claves publica y privada.  Este par de claves criptográficas pública y privada se usa al realizar la compilación para crear un ensamblado con nombre seguro.  Se puede generar un par de claves utilizando la [herramienta Nombre seguro \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md).  Normalmente, los archivos de par de claves tienen la extensión .snk.  
  
> [!NOTE]
>  En [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], las páginas de propiedades del proyecto de C\# y Visual Basic incluyen una pestaña **Firma** que permite seleccionar archivos de clave existentes o generar nuevos archivos de clave sin usa Sn.exe.  En Visual C\+\+, puede especificar la ubicación de un archivo de clave existente en la página de propiedades **Avanzadas**, en la sección **Vinculador** de la sección **Propiedades de configuración** de la ventana **Páginas de propiedades**.  El uso del atributo <xref:System.Reflection.AssemblyKeyFileAttribute> para identificar los pares de archivos de claves se ha quedado obsoleto a partir de [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].  
  
### Para crear un par de claves  
  
1.  En el símbolo del sistema, escriba el siguiente comando:  
  
     *nombre de archivo \<de* **sn –k** \>  
  
     En este comando, *nombre de archivo* es el nombre del archivo de salida que contiene el par de claves.  
  
 En el siguiente ejemplo se crea un par de claves denominado `sgKey.snk`.  
  
```  
sn -k sgKey.snk  
```  
  
 Si se piensa retrasar la firma de un ensamblado y se controla todo el par de claves \(lo que es improbable aparte de los escenarios de pruebas\), se pueden usar los comandos siguientes para generar un par de claves y, después, extraer de él la clave pública y ponerla en otro archivo.  Primero, cree el par de claves:  
  
```  
sn -k keypair.snk  
```  
  
-   Después, extraiga la clave pública del par de claves y cópiela en otro archivo:  
  
```  
sn -p keypair.snk public.snk  
```  
  
-   Una vez que haya creado el par de claves, debe ubicar el archivo donde las herramientas de firma de nombre seguro lo puedan encontrar.  
  
 Al firmar un ensamblado con un nombre seguro, la [herramienta Assembly Linker \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md) busca el archivo de clave en relación con el directorio actual y el directorio de salida.  Si se usan compiladores de la línea de comandos, no hay más que copiar la clave en el directorio actual que contenga los módulos de código.  
  
 Si está utilizando una versión anterior de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] que no cuenta con la ficha **Firma** en las propiedades de proyecto, la ubicación recomendada del archivo de clave es el directorio del proyecto con el atributo de archivo especificado tal y como se muestra a continuación:  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
## Vea también  
 [Crear y utilizar ensamblados con nombre seguro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)