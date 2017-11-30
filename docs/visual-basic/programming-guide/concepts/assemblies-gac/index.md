---
title: "Ensamblados y caché global de ensamblados (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fcf78ff1-f1ab-4a5d-b6d8-00d2046b6c80
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8a53a153851973c735a430056520b01c27b1ef59
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="assemblies-and-the-global-assembly-cache-visual-basic"></a>Ensamblados y caché global de ensamblados (Visual Basic)
Los ensamblados componen la unidad fundamental de implementación, control de versiones, reutilización, ámbito de activación y permisos de seguridad en una aplicación basada en .NET. Los ensamblados adoptan la forma de un archivo ejecutable (.exe) o de un archivo de biblioteca de vínculos dinámicos (.dll) y son bloques de compilación de .NET Framework. Proporcionan a Common Language Runtime la información necesaria para conocer las implementaciones de tipos. Puede pensar en un ensamblado como si fuera una colección de tipos y recursos que forman una unidad lógica de funcionalidad y se compilan para funcionar en conjunto.  
  
 Los ensamblados pueden contener uno o varios módulos. Por ejemplo, los proyectos más grandes pueden planearse de forma que varios desarrolladores individuales trabajen en módulos separados, que se unen para crear un ensamblado único. Para obtener más información sobre los módulos, vea el tema [Creación de un ensamblado de varios archivos](https://msdn.microsoft.com/library/226t7yxe).  
  
 Los ensamblados tienen las propiedades siguientes:  
  
-   Los ensamblados son archivos .exe o .dll implementados.  
  
-   Puede compartir un ensamblado entre aplicaciones colocándolo en la caché global de ensamblados. Los ensamblados deben tener un nombre seguro antes de que se puedan incluir en la caché global de ensamblados. Para más información, vea [Ensamblados con nombre seguro](https://msdn.microsoft.com/library/wd40t7ad).  
  
-   Los ensamblados solo se cargan en memoria si son necesarios. Si no se utilizan, no se cargan. Esto significa que los ensamblados pueden ser una manera eficaz de administrar recursos en proyectos más grandes.  
  
-   Mediante programación, puede obtener información sobre un ensamblado mediante reflexión. Para más información, vea [Reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).  
  
-   Si quiere cargar un ensamblado solo para inspeccionarlo, use un método como <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>.  
  
## <a name="assembly-manifest"></a>Manifiesto del ensamblado  
 Dentro de cada ensamblado hay un *manifiesto del ensamblado*. De forma similar a una tabla de contenido, el manifiesto del ensamblado contiene lo siguiente:  
  
-   La identidad del ensamblado (su nombre y versión).  
  
-   Una tabla de archivos que describe todos los demás archivos que componen el ensamblado, por ejemplo, cualquier otro ensamblado creado en que se basan los archivos .exe o .dll, o incluso archivos de mapa de bits o Léame.  
  
-   Una *lista de referencia de ensamblado*, que es una lista de todas las dependencias externas, archivos .dll u otros archivos que la aplicación necesita que alguien puede haber creado. Las referencias de ensamblado contienen referencias a objetos globales y privados. Los objetos globales residen en la caché global de ensamblados, un área disponible para otras aplicaciones, parecida al directorio System32. El espacio de nombres <xref:Microsoft.VisualBasic?displayProperty=nameWithType> es un ejemplo de un ensamblado en la caché global de ensamblados. Los objetos privados deben estar en un directorio del mismo nivel o debajo del directorio en el que se instala la aplicación.  
  
 Dado que los ensamblados contienen información sobre contenido, control de versiones y dependencias, las aplicaciones creadas con Visual Basic no dependen de los valores del Registro de Windows para funcionar correctamente. Los ensamblados reducen los conflictos de .dll y hacen las aplicaciones más confiables y fáciles de implementar. En muchos casos, puede instalar una aplicación basada en .NET con tan solo copiar sus archivos en el equipo de destino.  
  
 Para más información, vea [Manifiesto del ensamblado](https://msdn.microsoft.com/library/1w45z383).  
  
## <a name="adding-a-reference-to-an-assembly"></a>Incorporación de una referencia a un ensamblado  
 Para usar un ensamblado, debe agregar una referencia a él. A continuación, use la [instrucción Imports](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para elegir el espacio de nombres de los elementos que desea utilizar. Una vez que se hace referencia a un ensamblado y se importa, todas las clases accesibles, propiedades, métodos y otros miembros de sus espacios de nombres están disponibles para la aplicación como si su código formara parte del archivo de origen.  
  
## <a name="creating-an-assembly"></a>Creación de un ensamblado  
 Compile la aplicación desde la línea de comandos con el compilador de línea de comandos. Para obtener información detallada sobre la compilación de ensamblados desde la línea de comandos, vea [Compilar desde la línea de comandos](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
> [!NOTE]
>  Para compilar un ensamblado en Visual Studio, en el menú **Compilar**, seleccione **Compilar**.  
  
## <a name="see-also"></a>Vea también  
 [Ensamblados en Common Language Runtime](https://msdn.microsoft.com/library/k3677y81)  
 [Ensamblados de confianza (Visual Basic)](friend-assemblies.md)  
 [Cómo: compartir un ensamblado con otras aplicaciones (Visual Basic)](how-to-share-an-assembly-with-other-applications.md)  
 [Cómo: cargar y descargar ensamblados (Visual Basic)](how-to-load-and-unload-assemblies.md)  
 [Cómo: determinar si un archivo es un ensamblado (Visual Basic)](how-to-determine-if-a-file-is-an-assembly.md)  
 [Cómo: crear y utilizar ensamblados desde la línea de comandos (Visual Basic)](how-to-create-and-use-assemblies-using-the-command-line.md)  
 [Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (Visual Basic)](walkthrough-embedding-types-from-managed-assemblies-in-vs.md)  
 [Tutorial: inserción de información de tipos desde ensamblados de Microsoft Office en Visual Studio (Visual Basic)](walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-vs.md)
