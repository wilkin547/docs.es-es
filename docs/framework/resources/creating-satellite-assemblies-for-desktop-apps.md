---
title: Crear ensamblados satélite para aplicaciones de escritorio
description: Empiece a crear ensamblados satélite para aplicaciones de escritorio. Un ensamblado satélite se puede actualizar o reemplazar fácilmente para proporcionar recursos localizados.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- resource files, deploying
- hub-and-spoke resource deployment model
- resource files, packaging
- application resources, packaging
- public keys, obtaining
- satellite assemblies
- assemblies [.NET Framework], signing
- application resources, deploying
- Al.exe
- GAC (global assembly cache), satellite assemblies
- Assembly Linker
- directory locations for satellite assemblies
- global assembly cache, satellite assemblies
- packaging application resources
- compiling satellite assemblies
- re-signing assemblies
ms.assetid: 8d5c6044-2919-41d2-8321-274706b295ac
ms.openlocfilehash: 3e515028919518cb93cdbec3417eef061a512832
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558418"
---
# <a name="creating-satellite-assemblies-for-desktop-apps"></a>Crear ensamblados satélite para aplicaciones de escritorio

Los archivos de recursos desempeñan un papel fundamental en las aplicaciones localizadas. Permiten que una aplicación muestre cadenas, imágenes y otros datos en el idioma y la referencia cultural del usuario, y que proporcione datos alternativos si los recursos para el idioma o la referencia cultural del usuario no están disponibles. .NET Framework usa un modelo de concentrador y radio para buscar y recuperar recursos localizados. El concentrador es el ensamblado principal que contiene el código ejecutable no localizable y los recursos de una referencia cultural única, denominada referencia cultural neutra o predeterminada. La referencia cultural predeterminada es la referencia cultural de reserva de la aplicación y se usa si no hay recursos localizados disponibles. El atributo <xref:System.Resources.NeutralResourcesLanguageAttribute> se usa para designar la referencia cultural predeterminada de la aplicación. Cada radio se conecta a un ensamblado satélite que contiene los recursos de una única referencia cultural localizada, pero no contiene código. Debido a que los ensamblados satélite no forman parte del ensamblado principal, los recursos correspondientes a una referencia cultural específica se pueden actualizar o reemplazar fácilmente sin reemplazar el ensamblado principal de la aplicación.

> [!NOTE]
> Los recursos de la referencia cultural predeterminada de una aplicación también se pueden almacenar en un ensamblado satélite. Para ello, asigne al atributo <xref:System.Resources.NeutralResourcesLanguageAttribute> un valor de <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType>.

## <a name="satellite-assembly-name-and-location"></a>Nombre y ubicación del ensamblado satélite

El modelo de concentrador y radio requiere colocar recursos en ubicaciones específicas para que sea fácil ubicarlos y usarlos. Si no compila los recursos y les asigna el nombre de la manera prevista, o si no los coloca en las ubicaciones correctas, Common Language Runtime no podrá encontrarlos y usará en su lugar los recursos de la referencia cultural predeterminada. Para tener acceso automáticamente a los recursos localizados se usa el Administrador de recursos de .NET Framework, representado por un objeto <xref:System.Resources.ResourceManager>. El Administrador de recursos requiere lo siguiente:

- Todos los recursos de una referencia cultural determinada deben estar incluidos en un solo ensamblado satélite. En otras palabras, debe compilar varios archivos *.txt* o *.resx* en un solo archivo *.resources* binario.

- Debe haber un subdirectorio independiente en el directorio de la aplicación para cada referencia cultural localizada que almacena los recursos de esa referencia cultural. El nombre del subdirectorio debe ser el mismo que el nombre de la referencia cultural. Como alternativa, puede almacenar los ensamblados satélite en la caché global de ensamblados. En este caso, el componente de información de referencia cultural del nombre seguro del ensamblado debe indicar su referencia cultural. (Vea la sección [Instalar ensamblados satélite en la caché global de ensamblados](#SN) más adelante en este tema).

  > [!NOTE]
  > Si la aplicación incluye recursos para referencias culturales secundarias, coloque cada una de ellas en un subdirectorio independiente bajo el directorio de la aplicación. No coloque las referencias culturales secundarias en subdirectorios bajo el directorio de la referencia cultural principal.

- El ensamblado satélite debe tener el mismo nombre que la aplicación y debe usar la extensión de nombre de archivo ".resources.dll". Por ejemplo, si una aplicación se denomina *Example.exe*, el nombre de cada ensamblado satélite debe ser *Example.resources.dll*. Tenga en cuenta que el nombre del ensamblado satélite no indica la referencia cultural de sus archivos de recursos. Aun así, el ensamblado satélite aparece en un directorio que especifica la referencia cultural.

- La información sobre la referencia cultural del ensamblado satélite debe incluirse en los metadatos del ensamblado. Para almacenar el nombre de la referencia cultural en los metadatos del ensamblado satélite, especifique la opción `/culture` cuando use [Assembly Linker](../tools/al-exe-assembly-linker.md) para insertar recursos en el ensamblado satélite.

En la ilustración siguiente se muestran los requisitos de ejemplo de la estructura y la ubicación de los directorios para las aplicaciones que no se instalan en la [caché global de ensamblados](../app-domains/gac.md). Los elementos con las extensiones .txt y .resources no se incluirán en la aplicación final. Estos son los archivos de recursos intermedios que se usan para crear los ensamblados de recursos satélite finales. En este ejemplo, los archivos .resx se pueden sustituir por archivos .txt. Para obtener más información, vea [Packaging and Deploying Resources](packaging-and-deploying-resources-in-desktop-apps.md) (Empaquetar e implementar recursos).

La imagen siguiente muestra el directorio del ensamblado satélite:

![Un directorio de ensamblado satélite con subdirectorios de referencias culturas localizadas.](./media/creating-satellite-assemblies-for-desktop-apps/satellite-assembly-directory.gif)

## <a name="compiling-satellite-assemblies"></a>compilar ensamblados satélite

Use el [generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) para compilar archivos de texto o archivos XML ( *.resx*) que contienen recursos en archivos *.resources* binarios. Después, use [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) para compilar archivos *.resources* en ensamblados satélite. *Al.exe* crea un ensamblado a partir de los archivos *.resources* que especifique. Los ensamblados satélite solo pueden contener recursos; no pueden contener código ejecutable.

El siguiente comando de *Al.exe* crea un ensamblado satélite para la aplicación `Example` a partir del archivo de recursos de alemán *strings.de.resources*.

```console
al -target:lib -embed:strings.de.resources -culture:de -out:Example.resources.dll
```

El siguiente comando de *Al.exe* también crea un ensamblado satélite para la aplicación `Example` a partir del archivo *strings.de.resources*. La opción **/template** hace que el ensamblado satélite herede todos los metadatos del ensamblado salvo la información de referencia cultural del ensamblado principal (*Example.dll*).

```console
al -target:lib -embed:strings.de.resources -culture:de -out:Example.resources.dll -template:Example.dll
```  
  
En la siguiente tabla se describen detalladamente las opciones de *Al.exe* usadas en estos comandos:
  
|Opción|Descripción|
|------------|-----------------|
|`-target:lib`|Especifica que el ensamblado satélite se compila en un archivo de biblioteca (.dll). Dado que un ensamblado satélite no contiene código ejecutable y no es el ensamblado principal de la aplicación, debe guardar los ensamblados satélite como archivos DLL.|
|`-embed:strings.de.resources`|Especifica el nombre del archivo de recursos que se va a insertar cuando *Al.exe* compile el ensamblado. Puede insertar varios archivos .resources en un ensamblado satélite, pero si sigue el modelo de concentrador y radio, debe compilar un ensamblado satélite para cada referencia cultural. Aun así, puede crear archivos .resources independientes para cadenas y objetos.|
|`-culture:de`|Especifica la referencia cultural del recurso que se va a compilar. Common Language Runtime usa esta información cuando busca los recursos para la referencia cultural especificada. Si se omite esta opción, *Al.exe* compilará igualmente el recurso, pero el tiempo de ejecución no podrá encontrarlo cuando un usuario lo solicite.|
|`-out:Example.resources.dll`|Especifica el nombre del archivo de salida. El nombre debe seguir la convención de nomenclatura *baseName*.resources.*extension*, donde *baseName* es el nombre del ensamblado principal y *extension* es una extensión de nombre de archivo válida (por ejemplo, .dll). Tenga en cuenta que el tiempo de ejecución no puede determinar la referencia cultural de un ensamblado satélite a partir del nombre de su archivo de salida; debe usar la opción **/culture** para especificarla.|
|`-template:Example.dll`|Especifica el ensamblado del que el ensamblado satélite heredará todos los metadatos de ensamblado, salvo el campo correspondiente a la referencia cultural. Esta opción solo afecta a los ensamblados satélite si se especifica un ensamblado con [nombre seguro](../../standard/assembly/strong-named.md).|
  
 Para obtener una lista completa de las opciones disponibles con *Al.exe*, vea [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md).
  
## <a name="satellite-assemblies-an-example"></a>Ensamblados satélite: Un ejemplo

A continuación se incluye un ejemplo sencillo de "Hola a todos" que muestra un cuadro de mensaje con un saludo localizado. El ejemplo incluye recursos para las referencias culturales de inglés (Estados Unidos), francés (Francia) y ruso (Rusia), y su referencia cultural de reserva es inglés. Para crear este ejemplo, haga lo siguiente:
  
1. Cree un archivo de recursos denominado *Greeting.resx* o *Greeting.txt* para que contenga el recurso para la referencia cultural predeterminada. Almacene una sola cadena denominada `HelloString` cuyo valor sea "Hola a todos" en este archivo.

2. Para indicar que el inglés (en) es la referencia cultural predeterminada de la aplicación, agregue el siguiente atributo <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=nameWithType> al archivo AssemblyInfo de la aplicación o al archivo de código fuente principal que se compilará en el ensamblado principal de la aplicación.

    ```csharp
    [assembly: NeutralResourcesLanguageAttribute("en")]
    ```

    ```vb
    <Assembly: NeutralResourcesLanguageAttribute("en")>
    ```
  
3. Agregue compatibilidad para referencias culturales adicionales (en-US, fr-FR y ru-RU) a la aplicación de la manera siguiente:  
  
    - Para admitir la referencia cultural en-US o inglés (Estados Unidos), cree un archivo de recursos denominado *Greeting.en-US.resx* o *Greeting.en-US.txt* y almacene en él una sola cadena denominada `HelloString` cuyo valor sea "Hi world!".
  
    - Para admitir la referencia cultural fr-FR o francés (Francia), cree un archivo de recursos denominado *Greeting.fr-FR.resx* o *Greeting.fr-FR.txt* y almacene en él una sola cadena denominada `HelloString` cuyo valor sea "Salut tout le monde!".
  
    - Para admitir la referencia cultural ru-RU o ruso (Rusia), cree un archivo de recursos denominado *Greeting.ru-RU.resx* o *Greeting.ru-RU.txt* y almacene en él una sola cadena denominada `HelloString` cuyo valor sea "Всем привет!".
  
4. Use [Resgen.exe](../tools/resgen-exe-resource-file-generator.md) para compilar cada texto o archivo de recursos XML en un archivo *.resources* binario. La salida es un conjunto de archivos que tienen el mismo nombre de archivo raíz, como los archivos *.resx* o *.txt*, pero con una extensión *.resources*. Si crea el ejemplo con Visual Studio, el proceso de compilación se realiza automáticamente. Si no está usando Visual Studio, ejecute los comandos siguientes para compilar los archivos *.resx* en archivos *.resources*:  
  
    ```console
    resgen Greeting.resx
    resgen Greeting.en-us.resx
    resgen Greeting.fr-FR.resx
    resgen Greeting.ru-RU.resx
    ```

    Si los recursos se encuentran en archivos de texto en lugar de archivos XML, cambie la extensión *.resx* a *.txt*.

5. Compile el código fuente siguiente junto con los recursos para la referencia cultural predeterminada en el ensamblado principal de la aplicación:

    > [!IMPORTANT]
    > Si usa la línea de comandos en lugar de Visual Studio para crear el ejemplo, debe modificar la llamada al constructor de clase <xref:System.Resources.ResourceManager> de la siguiente manera: `ResourceManager rm = new ResourceManager("Greetings", typeof(Example).Assembly);`

    [!code-csharp[Conceptual.Resources.Locating#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.locating/cs/program.cs#1)]
    [!code-vb[Conceptual.Resources.Locating#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.locating/vb/module1.vb#1)]

    Si la aplicación se denomina Example y está compilando desde la línea de comandos, el comando del compilador de C# es el siguiente:

    ```console
    csc Example.cs -res:Greeting.resources
    ```

    El comando de compilador de Visual Basic correspondiente es el siguiente:

    ```console
    vbc Example.vb -res:Greeting.resources
    ```

6. Cree un subdirectorio en el directorio principal de la aplicación para cada referencia cultural localizada admitida por la aplicación. Debe crear un subdirectorio *en-US*, *fr-FR* y *ru-RU*. Visual Studio crea estos subdirectorios automáticamente como parte del proceso de compilación.

7. Inserte los archivos *.resources* individuales específicos de la referencia cultural en ensamblados satélite y guárdelos en el directorio adecuado. El comando para hacer esto para cada archivo *.resources* es el siguiente:

    ```console
    al -target:lib -embed:Greeting.culture.resources -culture:culture -out:culture\Example.resources.dll
    ```

     donde *culture* es el nombre de la referencia cultural cuyos recursos contiene el ensamblado satélite. Visual Studio controla este proceso automáticamente.

Después, ya puede ejecutar el ejemplo. Seleccionará aleatoriamente como referencia cultural actual una de las referencias culturales admitidas y mostrará un saludo localizado.

<a name="SN"></a>

## <a name="installing-satellite-assemblies-in-the-global-assembly-cache"></a>Instalar ensamblados satélite en la caché global de ensamblados

En lugar de instalar los ensamblados en el subdirectorio de una aplicación local, puede instalarlos en la caché global de ensamblados. Esto es especialmente útil si tiene bibliotecas de clases y ensamblados de recursos de bibliotecas de clases que usan varias aplicaciones.
  
Para instalar ensamblados en la caché global de ensamblados, es necesario que tengan nombres seguros. Los ensamblados con nombre seguro se firman con un par de claves pública y privada válido. Contienen información de versión que el tiempo de ejecución usa para determinar qué ensamblado debe usar para atender a una solicitud de enlace. Para obtener más información sobre los nombres seguros y las versiones, vea [Assembly Versioning](../../standard/assembly/versioning.md) (Versiones de los ensamblados). Para obtener más información sobre los nombres seguros, vea [Strong-Named Assemblies](../../standard/assembly/strong-named.md) (Ensamblados con nombre seguro).

Cuando esté desarrollando una aplicación, es poco probable que tenga acceso al par de claves pública y privada final. Para instalar un ensamblado satélite en la caché global de ensamblados y asegurarse de que funciona según lo previsto, puede usar una técnica denominada firma retardada. Cuando se retrasa la firma de un ensamblado, en tiempo de compilación se reserva espacio en el archivo para la firma de nombre seguro. La firma real se retrasa hasta más adelante, cuando esté disponible el par de claves pública y privada final. Para obtener más información sobre la firma retardada, vea [Delay Signing an Assembly](../../standard/assembly/delay-sign.md) (Retrasar la firma de un ensamblado).

### <a name="obtaining-the-public-key"></a>Obtener la clave pública

Para retrasar la firma de un ensamblado, debe tener acceso a la clave pública. Puede obtener la clave pública real de la organización que se encargará de la firma, o bien puede crear una clave pública mediante la [herramienta de nombre seguro (Sn.exe)](../tools/sn-exe-strong-name-tool.md).

El siguiente comando de *Sn.exe* crea un par de claves pública y privada de prueba. La opción **–k** especifica que *Sn.exe* debe crear un par de claves y guardarlo en un archivo denominado *TestKeyPair.snk*.
  
```console
sn –k TestKeyPair.snk
```

Puede extraer la clave pública del archivo que contiene el par de claves de prueba. El siguiente comando extrae la clave pública de *TestKeyPair.snk* y la guarda en *PublicKey.snk*:

```console
sn –p TestKeyPair.snk PublicKey.snk
```

### <a name="delay-signing-an-assembly"></a>Retrasar la firma de un ensamblado

Después de obtener o crear la clave pública, use [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) para compilar el ensamblado y especificar la firma retardada.

El siguiente comando de *Al.exe* crea un ensamblado satélite con nombre seguro para la aplicación StringLibrary a partir del archivo *strings.ja.resources*:

```console
al -target:lib -embed:strings.ja.resources -culture:ja -out:StringLibrary.resources.dll -delay+ -keyfile:PublicKey.snk
```

La opción **-delay+** especifica que Assembly Linker debe retrasar la firma del ensamblado. La opción **-keyfile** especifica el nombre del archivo de claves que contiene la clave pública que se va a usar para retrasar la firma del ensamblado.

### <a name="re-signing-an-assembly"></a>Volver a firmar un ensamblado

Antes de implementar la aplicación, debe volver a firmar el ensamblado satélite con firma retrasada mediante el par de claves real. Para ello, use *Sn.exe*.

El siguiente comando de *Sn.exe* firma *StringLibrary.resources.dll* con el par de claves almacenado en el archivo *RealKeyPair.snk*. La opción **–R** especifica que se debe volver a firmar un ensamblado ya firmado o con firma retrasada.

```console
sn –R StringLibrary.resources.dll RealKeyPair.snk
```

### <a name="installing-a-satellite-assembly-in-the-global-assembly-cache"></a>Instalar un ensamblado satélite en la caché global de ensamblados

Cuando el tiempo de ejecución busca recursos en el proceso de reserva de recursos, busca primero en la [caché global de ensamblados](../app-domains/gac.md). (Para obtener más información, vea la sección sobre el proceso de reserva de recursos del tema [Packaging and Deploying Resources](packaging-and-deploying-resources-in-desktop-apps.md) (Empaquetar e implementar recursos)). En cuanto se firma un ensamblado satélite con un nombre seguro, puede instalarse en la caché global de ensamblados mediante la [herramienta Caché global de ensamblados (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md).

El siguiente comando de *Gacutil.exe* instala *StringLibrary.resources.dll** en la memoria caché global de ensamblados:

```console
gacutil -i:StringLibrary.resources.dll
```

La opción **/i** especifica que *Gacutil.exe* debe instalar el ensamblado especificado en la memoria caché global de ensamblados. Una vez que se ha instalado el ensamblado satélite en la caché, los recursos que contiene están disponibles para todas las aplicaciones que están diseñadas para usar el ensamblado satélite.

### <a name="resources-in-the-global-assembly-cache-an-example"></a>Recursos en la caché global de ensamblados: Un ejemplo

En el ejemplo siguiente se usa un método en una biblioteca de clases de .NET Framework para extraer y devolver un saludo localizado de un archivo de recursos. La biblioteca y sus recursos están registrados en la caché global de ensamblados. El ejemplo incluye recursos para las referencias culturales de inglés (Estados Unidos), francés (Francia), ruso (Rusia) e inglés. El inglés es la referencia cultural predeterminada y sus recursos están almacenados en el ensamblado principal. En el ejemplo inicialmente se retrasa la firma de la biblioteca y sus ensamblados satélite con una clave pública y, después, se vuelven a firmar con un par de claves pública y privada. Para crear este ejemplo, haga lo siguiente:

1. Si no está usando Visual Studio, use el siguiente comando de la [herramienta de nombre seguro (Sn.exe)](../tools/sn-exe-strong-name-tool.md) para crear un par de claves pública y privada denominado *ResKey.snk*:

    ```console
    sn –k ResKey.snk
    ```

    Si está usando Visual Studio, use la pestaña **Firma** del cuadro de diálogo **Propiedades** del proyecto para generar el archivo de clave.

2. Use el siguiente comando de la [herramienta de nombre seguro (Sn.exe)](../tools/sn-exe-strong-name-tool.md) para crear un archivo de clave pública denominado *PublicKey.snk*:

    ```console
    sn –p ResKey.snk PublicKey.snk
    ```

3. Cree un archivo de recursos denominado *Strings.resx* para que contenga el recurso para la referencia cultural predeterminada. Almacene una sola cadena denominada `Greeting` cuyo valor sea "¿Qué tal?" en ese archivo.

4. Para indicar que "en" es la referencia cultural predeterminada de la aplicación, agregue el siguiente atributo <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=nameWithType> al archivo AssemblyInfo de la aplicación o al archivo de código fuente principal que se compilará en el ensamblado principal de la aplicación:

    [!code-csharp[Conceptual.Resources.Satellites#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/stringlibrary.cs#2)]
    [!code-vb[Conceptual.Resources.Satellites#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/stringlibrary.vb#2)]

5. Agregue compatibilidad para referencias culturales adicionales (en-US, fr-FR y ru-RU) a la aplicación de la manera siguiente:

    - Para admitir la referencia cultural "en-US" o inglés (Estados Unidos), cree un archivo de recursos denominado *Strings.en-US.resx* o *Strings.en-US.txt* y almacene en él una sola cadena denominada `Greeting` cuyo valor sea "Hello!".

    - Para admitir la referencia cultural "fr-FR" o francés (Francia), cree un archivo de recursos denominado *Strings.fr-FR.resx* o *Strings.fr-FR.txt* y almacene en él una sola cadena denominada `Greeting` cuyo valor sea "Bonjour!".

    - Para admitir la referencia cultural "ru-RU" o ruso (Rusia), cree un archivo de recursos denominado *Strings.ru-RU.resx* o *Strings.ru-RU.txt* y almacene en él una sola cadena denominada `Greeting` cuyo valor sea "Привет!".

6. Use [Resgen.exe](../tools/resgen-exe-resource-file-generator.md) para compilar cada texto o archivo de recursos XML en un archivo .resources binario. La salida es un conjunto de archivos que tienen el mismo nombre de archivo raíz, como los archivos *.resx* o *.txt*, pero con una extensión *.resources*. Si crea el ejemplo con Visual Studio, el proceso de compilación se realiza automáticamente. Si no está usando Visual Studio, ejecute el comando siguiente para compilar los archivos *.resx* en archivos *.resources*:

    ```console
    resgen filename
    ```

    Donde *filename* es la ruta de acceso opcional, el nombre de archivo y la extensión del archivo *.resx* o de texto.

7. Compile el siguiente código fuente para *StringLibrary.vb* o *StringLibrary.cs* junto con los recursos para la referencia cultural predeterminada en un ensamblado de biblioteca con firma retrasada denominado *StringLibrary.dll*:

    > [!IMPORTANT]
    > Si usa la línea de comandos en lugar de Visual Studio para crear el ejemplo, debe modificar la llamada al constructor de clase <xref:System.Resources.ResourceManager> de la siguiente manera: `ResourceManager rm = new ResourceManager("Strings",` `typeof(Example).Assembly);`.

    [!code-csharp[Conceptual.Resources.Satellites#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/stringlibrary.cs#1)]
    [!code-vb[Conceptual.Resources.Satellites#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/stringlibrary.vb#1)]

    El comando para el compilador de C# es el siguiente:

    ```console
    csc -t:library -resource:Strings.resources -delaysign+ -keyfile:publickey.snk StringLibrary.cs
    ```

    El comando de compilador de Visual Basic correspondiente es el siguiente:

    ```console
    vbc -t:library -resource:Strings.resources -delaysign+ -keyfile:publickey.snk StringLibrary.vb
    ```

8. Cree un subdirectorio en el directorio principal de la aplicación para cada referencia cultural localizada admitida por la aplicación. Debe crear un subdirectorio *en-US*, *fr-FR* y *ru-RU*. Visual Studio crea estos subdirectorios automáticamente como parte del proceso de compilación. Dado que todos los ensamblados satélite tienen el mismo nombre de archivo, se usan los subdirectorios para almacenar los ensamblados satélite individuales específicos de la referencia cultural hasta que se firmen con un par de claves pública y privada.

9. Inserte los archivos *.resources* individuales específicos de la referencia cultural en ensamblados satélite con firma retrasada y guárdelos en el directorio adecuado. El comando para hacer esto para cada archivo *.resources* es el siguiente:

    ```console
    al -target:lib -embed:Strings.culture.resources -culture:culture -out:culture\StringLibrary.resources.dll -delay+ -keyfile:publickey.snk
    ```

    donde *culture* es el nombre de una referencia cultural. En este ejemplo, los nombres de referencia cultural son en-US, fr-FR y ru-RU.

10. Vuelva a firmar *StringLibrary.dll* usando la [herramienta de nombre seguro (Sn.exe)](../tools/sn-exe-strong-name-tool.md) de la manera siguiente:

    ```console
    sn –R StringLibrary.dll RealKeyPair.snk
    ```

11. Vuelva a firmar los ensamblados satélite individuales. Para ello, use la [herramienta de nombre seguro (Sn.exe)](../tools/sn-exe-strong-name-tool.md) como se indica a continuación para cada ensamblado satélite:

    ```console
    sn –R StringLibrary.resources.dll RealKeyPair.snk
    ```

12. Registre *StringLibrary.dll* y cada uno de sus ensamblados satélite en la memoria caché global de ensamblados usando el siguiente comando:

    ```console
    gacutil -i filename
    ```

    donde *filename* es el nombre del archivo que se va a registrar.

13. Si está usando Visual Studio, cree un proyecto de **aplicación de consola** denominado `Example`, agréguele una referencia a *StringLibrary.dll* y el siguiente código fuente, y compílelo.

    [!code-csharp[Conceptual.Resources.Satellites#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/example.cs#3)]
    [!code-vb[Conceptual.Resources.Satellites#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/example.vb#3)]

    Para compilar desde la línea de comandos, use el comando siguiente para el compilador de C#:

    ```console
    csc Example.cs -r:StringLibrary.dll
    ```

    La línea de comandos para el compilador de Visual Basic es la siguiente:

    ```console
    vbc Example.vb -r:StringLibrary.dll
    ```

14. Ejecute *Example.exe*.

## <a name="see-also"></a>Vea también

- [Empaquetar e implementar recursos](packaging-and-deploying-resources-in-desktop-apps.md)
- [Retrasar la firma de un ensamblado](../../standard/assembly/delay-sign.md)
- [Al.exe (Assembly Linker)](../tools/al-exe-assembly-linker.md)
- [Sn.exe (Herramienta de nombre seguro)](../tools/sn-exe-strong-name-tool.md)
- [Gacutil.exe (Herramienta Caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md)
- [Recursos de aplicaciones de escritorio](index.md)
