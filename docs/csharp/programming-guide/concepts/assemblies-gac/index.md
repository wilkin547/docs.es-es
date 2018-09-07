---
title: Ensamblados y caché global de ensamblados (C#)
ms.date: 07/20/2015
ms.assetid: 149f5ca5-5b34-4746-9542-1ae43b2d0256
ms.openlocfilehash: ed5ecff57035b4d3cf47f8325fe5c172180f9d40
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042301"
---
# <a name="assemblies-and-the-global-assembly-cache-c"></a>Ensamblados y caché global de ensamblados (C#)
Los ensamblados componen la unidad fundamental de implementación, control de versiones, reutilización, ámbito de activación y permisos de seguridad en una aplicación basada en .NET. Los ensamblados adoptan la forma de un archivo ejecutable (.exe) o de un archivo de biblioteca de vínculos dinámicos (.dll) y son bloques de compilación de .NET Framework. Proporcionan a Common Language Runtime la información necesaria para conocer las implementaciones de tipos. Puede pensar en un ensamblado como si fuera una colección de tipos y recursos que forman una unidad lógica de funcionalidad y se compilan para funcionar en conjunto.  
  
 Los ensamblados pueden contener uno o varios módulos. Por ejemplo, los proyectos más grandes pueden planearse de forma que varios desarrolladores individuales trabajen en módulos separados, que se unen para crear un ensamblado único. Para obtener más información sobre los módulos, vea el tema [Creación de un ensamblado de varios archivos](../../../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md).  
  
 Los ensamblados tienen las propiedades siguientes:  
  
-   Los ensamblados son archivos .exe o .dll implementados.  
  
-   Puede compartir un ensamblado entre aplicaciones colocándolo en la caché global de ensamblados. Los ensamblados deben tener un nombre seguro antes de que se puedan incluir en la caché global de ensamblados. Para más información, vea [Ensamblados con nombre seguro](../../../../../docs/framework/app-domains/strong-named-assemblies.md).  
  
-   Los ensamblados solo se cargan en memoria si son necesarios. Si no se utilizan, no se cargan. Esto significa que los ensamblados pueden ser una manera eficaz de administrar recursos en proyectos más grandes.  
  
-   Mediante programación, puede obtener información sobre un ensamblado mediante reflexión. Para obtener más información, vea [Reflexión (C#)](../../../../csharp/programming-guide/concepts/reflection.md).  
  
-   Si quiere cargar un ensamblado solo para inspeccionarlo, use un método como <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>.  
  
## <a name="assembly-manifest"></a>Manifiesto del ensamblado  
 Dentro de cada ensamblado hay un *manifiesto del ensamblado*. De forma similar a una tabla de contenido, el manifiesto del ensamblado contiene lo siguiente:  
  
-   La identidad del ensamblado (su nombre y versión).  
  
-   Una tabla de archivos que describe todos los demás archivos que componen el ensamblado, por ejemplo, cualquier otro ensamblado creado en que se basan los archivos .exe o .dll, o incluso archivos de mapa de bits o Léame.  
  
-   Una *lista de referencia de ensamblado*, que es una lista de todas las dependencias externas, archivos .dll u otros archivos que la aplicación necesita que alguien puede haber creado. Las referencias de ensamblado contienen referencias a objetos globales y privados. Los objetos globales residen en la caché global de ensamblados, un área disponible para otras aplicaciones. Los objetos privados deben estar en un directorio del mismo nivel o debajo del directorio en el que se instala la aplicación.  
  
 Dado que los ensamblados contienen información sobre contenido, control de versiones y dependencias, las aplicaciones creadas con C# no dependen de los valores del Registro de Windows para funcionar correctamente. Los ensamblados reducen los conflictos de .dll y hacen las aplicaciones más confiables y fáciles de implementar. En muchos casos, puede instalar una aplicación basada en .NET con tan solo copiar sus archivos en el equipo de destino.  
  
 Para más información, vea [Manifiesto del ensamblado](../../../../../docs/framework/app-domains/assembly-manifest.md).  
  
## <a name="adding-a-reference-to-an-assembly"></a>Incorporación de una referencia a un ensamblado  
 Para usar un ensamblado, debe agregar una referencia a él. Después, use la [directiva using](../../../../csharp/language-reference/keywords/using-directive.md) para elegir el espacio de nombres de los elementos que quiere usar. Una vez que se hace referencia a un ensamblado y se importa, todas las clases accesibles, propiedades, métodos y otros miembros de sus espacios de nombres están disponibles para la aplicación como si su código formara parte del archivo de origen.  
  
 En C#, también puede usar dos versiones del mismo ensamblado en una sola aplicación. Para obtener más información, vea [alias externo](../../../../csharp/language-reference/keywords/extern-alias.md).  
  
## <a name="creating-an-assembly"></a>Creación de un ensamblado  
 Para compilar la aplicación, haga clic en **Compilar** en el menú **Compilar** o compílela desde la línea de comandos con el compilador de línea de comandos. Para obtener información detallada sobre la compilación de ensamblados desde la línea de comandos, vea [Compilar la línea de comandos con csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  
  
> [!NOTE]
>  Para compilar un ensamblado en Visual Studio, en el menú **Compilar**, seleccione **Compilar**.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../../csharp/programming-guide/index.md)  
- [Ensamblados en Common Language Runtime](../../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
- [Ensamblados de confianza (C#)](friend-assemblies.md)  
- [Uso compartido de un ensamblado con otras aplicaciones (C#)](how-to-share-an-assembly-with-other-applications.md)  
- [Carga y descarga de ensamblados (C#)](how-to-load-and-unload-assemblies.md)  
- [Determinar si un archivo es un ensamblado (C#)](how-to-determine-if-a-file-is-an-assembly.md)  
- [Creación y uso de ensamblados con la línea de comandos (C#)](how-to-create-and-use-assemblies-using-the-command-line.md)  
- [Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio (C#)](walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
- [Tutorial: Insertar información de tipos de los ensamblados de Microsoft Office en Visual Studio (C#)](walkthrough-embedding-type-information-from-microsoft-office-assemblies.md)
