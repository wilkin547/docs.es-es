---
description: 'Más información acerca de: BC30145: no se puede emitir el ensamblado: <error message>'
title: 'No se puede emitir el ensamblado: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 015ab6e1d186495d72bddd65678ab15088c0f1b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674888"
---
# <a name="bc30145-unable-to-emit-assembly-error-message"></a>BC30145: no se puede emitir el ensamblado: \<error message>

El compilador Visual Basic llama a Assembly Linker (*Al.exe*, también conocido como ALink) para generar un ensamblado con un manifiesto, y el vinculador informa de un error en la fase de emisión de la creación del ensamblado.

**Identificador de error:** BC30145

## <a name="to-correct-this-error"></a>Para corregir este error

1. Examine el mensaje de error citado y consulte el tema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) para obtener una explicación más detallada y consejos.

2. Intente firmar el ensamblado manualmente, mediante el [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) o el [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md).

3. Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.

### <a name="to-sign-the-assembly-manually"></a>Para firmar el ensamblado manualmente

1. Use el [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)) para crear un archivo de par de claves pública y privada.

   Este archivo tiene la extensión *. snk* .

2. Elimine la referencia COM que está provocando el error en el proyecto.

3. Abra el [símbolo del sistema para desarrolladores para Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

   En Windows 10, escriba **símbolo del sistema para desarrolladores** en el cuadro de búsqueda de la barra de tareas. A continuación, seleccione **símbolo del sistema para desarrolladores para VS 2017** en la lista de resultados.

4. Cambie el directorio al directorio en el que desea colocar el contenedor de ensamblado.

5. Escriba el comando siguiente:

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   Un ejemplo del comando real que puede escribir es:

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > Utilice comillas dobles si una ruta de acceso o archivo contiene espacios.

6. En Visual Studio, agregue una referencia de ensamblado .NET al archivo que acaba de crear.

## <a name="see-also"></a>Vea también

- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Sn.exe (Herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)
- [Cómo: Creación de un par de claves privada y pública](../../../standard/assembly/create-public-private-key-pair.md)
- [Hable con nosotros](/visualstudio/ide/feedback-options)
