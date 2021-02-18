---
description: Más información sobre -keyfile
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 6d19f136d5961e8a933380164a3a77055e1da329
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466944"
---
# <a name="-keyfile"></a>-keyfile

Especifica un archivo que contiene una clave o un par de claves que asigna un nombre seguro al ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumentos  

 `file`  
 Obligatorio. Archivo que contiene la clave. Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").  
  
## <a name="remarks"></a>Comentarios  

 El compilador inserta la clave pública en el manifiesto del ensamblado y firma después el ensamblado final con la clave privada. Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos. Para obtener más información, consulte [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
 Si se compila con `-target:module`, el nombre del archivo de claves se mantiene en el módulo y se incorpora al ensamblado que se crea al compilar un ensamblado con [-addmodule](addmodule.md).  
  
 También puede pasar la información de cifrado al compilador con [-keycontainer](keycontainer.md). Use [-delaysign](delaysign.md) para firmar el ensamblado de forma parcial.  
  
 También se puede especificar esta opción como atributo personalizado (<xref:System.Reflection.AssemblyKeyFileAttribute>) en el código fuente de cualquier módulo de Lenguaje Intermedio de Microsoft.  
  
 Si en una misma compilación se especifica tanto `-keyfile` como [-keycontainer](keycontainer.md) (ya sea mediante una opción de línea de comandos o mediante un atributo personalizado), el compilador probará primero el contenedor de claves. Si lo consigue, el ensamblado se firma con la información del contenedor de claves. Si el compilador no encuentra el contenedor de claves, probará el archivo especificado con `-keyfile`. Si lo consigue, el ensamblado se firma con la información del archivo de claves, y la información de la clave se instalará en el contenedor de claves (similar a `sn -i`) de modo que, en la próxima compilación, el contenedor de claves será válido.  
  
 Tenga en cuenta que un archivo de clave puede contener solo la clave pública.  
  
 Consulte [Creación y uso de ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) para obtener más información sobre cómo firmar un ensamblado.  
  
> [!NOTE]
> La opción `-keyfile` no está disponible en el entorno de desarrollo de Visual Studio; solo lo está cuando se compila desde la línea de comandos.

## <a name="example"></a>Ejemplo

En el código siguiente se compila el archivo de código fuente `Input.vb` y se especifica un archivo de claves.

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Compilador de línea de comandos de Visual Basic](index.md)
- [-reference (Visual Basic)](reference.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
