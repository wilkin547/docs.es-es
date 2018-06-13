---
title: 'Cómo: Crear un par de claves privada y pública'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe799e15655d4ae1d9d9b7303728b503a5e45082
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741755"
---
# <a name="how-to-create-a-public-private-key-pair"></a>Cómo: Crear un par de claves privada y pública
Para firmar un ensamblado con un nombre seguro, debe disponer de un par de claves privada/pública. Este par de claves criptográficas pública y privada se utiliza durante la compilación para crear un ensamblado con un nombre seguro. Puede crear un par de claves utilizando la [Herramienta Nombre seguro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md). Normalmente, los archivos de par de claves tienen la extensión snk.  
  
> [!NOTE]
>  En Visual Studio, las páginas de propiedades de proyecto de C# y Visual Basic incluyen una pestaña **Firma** que le permite seleccionar los archivos de clave existentes o generar nuevos archivos de clave sin Sn.exe. En Visual C++, puede especificar la ubicación de un archivo de clave existente en la página de propiedades **Avanzadas** de la sección **Vinculador** de la sección **Propiedades de configuración** de la ventana **Páginas de propiedades**. El uso del atributo <xref:System.Reflection.AssemblyKeyFileAttribute> para identificar los pares de archivo de clave se ha quedado obsoleto empezando por [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].  
  
### <a name="to-create-a-key-pair"></a>Para crear un par de claves  
  
1.  En el símbolo del sistema, escriba el siguiente comando:  
  
     **sn –k** \<*nombre de archivo*>  
  
     En este comando, *nombre de archivo* es el nombre del archivo de salida que contiene el par de claves.  
  
 En el siguiente ejemplo se crea un par de claves denominado `sgKey.snk`.  
  
```  
sn -k sgKey.snk  
```  
  
 Si desea retrasar la firma de un ensamblado y controlar el par de claves completo (que es poco probable que esté fuera de los escenarios de prueba), puede usar los siguientes comandos para generar un par de claves y, a continuación, extraer la clave pública a partir de él en un archivo independiente. Primero, cree el par de claves:  
  
```  
sn -k keypair.snk  
```  
  
 A continuación, extraiga la clave pública del par de claves y cópiela en un archivo independiente:  
  
```  
sn -p keypair.snk public.snk  
```  
  
 Una vez creado el par de claves, debe colocar el archivo donde las herramientas de inicio de sesión de nombre seguro puedan encontrarlo.  
  
 Al firmar un ensamblado con un nombre seguro, la [herramienta Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) busca el archivo de clave en relación con el directorio actual y el directorio de salida. Si se usan compiladores de la línea de comandos, no hay más que copiar la clave en el directorio actual que contenga los módulos de código.  
  
 Si está usando una versión anterior de Visual Studio que no tiene una pestaña **Firma** en las propiedades del proyecto, la ubicación recomendada del archivo de clave es el directorio del proyecto con el atributo de archivo especificado de la siguiente forma:  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
## <a name="see-also"></a>Vea también  
 [Crear y utilizar ensamblados con nombre seguro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
