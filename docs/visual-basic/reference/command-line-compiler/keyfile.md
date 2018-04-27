---
title: -keyfile
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 319d01e8162dbc3806b0d9ba59e90410acb1acd5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="-keyfile"></a>-keyfile
Especifica un archivo que contiene una clave o un par de claves que asigna un nombre seguro al ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumentos  
 `file`  
 Requerido. Archivo que contiene la clave. Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas ("").  
  
## <a name="remarks"></a>Comentarios  
 El compilador inserta la clave pública en el manifiesto del ensamblado y firma después el ensamblado final con la clave privada. Para generar un archivo de clave, escriba `sn -k file` en la línea de comandos. Para obtener más información, consulte [Sn.exe (herramienta de nombre seguro)][Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Si se compila con `-target:module`, el nombre del archivo de clave se mantiene en el módulo y se incorpora en el ensamblado que se crea cuando se compila un ensamblado con [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 También puede pasar la información de cifrado al compilador con [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar el ensamblado de forma parcial.  
  
 También puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyFileAttribute>) en el código fuente de cualquier módulo de lenguaje intermedio de Microsoft.  
  
 En caso de ambos `-keyfile` y [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) se especifican (ya sea mediante una opción de línea de comandos o mediante un atributo personalizado) en la misma compilación, el compilador intenta utilizar primero el contenedor de claves. Si lo consigue, el ensamblado se firma con la información del contenedor de claves. Si el compilador no encuentra el contenedor de claves, trata el archivo especificado con `-keyfile`. Si se ejecuta correctamente, el ensamblado se firma con la información en el archivo de clave y la información de clave se instala en el contenedor de claves (similar a `sn -i`) para que en la siguiente compilación, el contenedor de claves será válido.  
  
 Tenga en cuenta que un archivo de clave puede contener solo la clave pública.  
  
 Vea [crear y utilizar ensamblados](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) para obtener más información sobre cómo firmar un ensamblado.  
  
> [!NOTE]
>  El `-keyfile` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila el archivo de código fuente `Input.vb` y especifica un archivo de clave.  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Ensamblados y Caché global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-referencia (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
