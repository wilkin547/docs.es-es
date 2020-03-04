---
title: Cómo realizar una transformación XSLT mediante un ensamblado
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 76ee440b-d134-4f8f-8262-b917ad6dcbf6
ms.openlocfilehash: 447cf18c7a9d24addf9d0a4ad523f46a45a5d27a
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155980"
---
# <a name="how-to-perform-an-xslt-transformation-by-using-an-assembly"></a><span data-ttu-id="71164-102">Cómo realizar una transformación XSLT mediante un ensamblado</span><span class="sxs-lookup"><span data-stu-id="71164-102">How to: Perform an XSLT Transformation by Using an Assembly</span></span>
<span data-ttu-id="71164-103">El compilador XSLT (xsltc.exe) compila hojas de estilo XSLT y genera un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="71164-103">The XSLT compiler (xsltc.exe) compiles XSLT style sheets and generates an assembly.</span></span> <span data-ttu-id="71164-104">Dicho ensamblado se puede pasar directamente al método <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="71164-104">The assembly can be passed directly into the <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> method.</span></span>  
  
### <a name="to-copy-the-xml-and-xslt-files-to-your-local-computer"></a><span data-ttu-id="71164-105">Para copiar los archivos XML y XSLT al ordenador</span><span class="sxs-lookup"><span data-stu-id="71164-105">To copy the XML and XSLT files to your local computer</span></span>  
  
- <span data-ttu-id="71164-106">Copie el archivo XSLT en su ordenador y llámelo Transform.xsl.</span><span class="sxs-lookup"><span data-stu-id="71164-106">Copy the XSLT file to your local computer and name it Transform.xsl.</span></span>  
  
    ```xml  
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
      xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
      xmlns:user="urn:my-scripts">  
      <msxsl:script language="C#" implements-prefix="user">  
        <![CDATA[  
      public string discount(string price){  
        char[] trimChars = { '$' };  
        //trim leading $, convert price to type double  
        double discount_value = Convert.ToDouble(price.TrimStart(trimChars));  
        //apply 10% discount and round appropriately  
        discount_value = .9*discount_value;  
        //convert value to decimal and format as currency  
        string discount_price = discount_value.ToString("C");  
        return discount_price;  
      }  
      ]]>  
      </msxsl:script>  
      <xsl:template match="catalog">  
        <html>  
          <head></head>  
          <body>  
            <table border="1">  
              <tr>  
                <th align="left">Title</th>  
                <th align="left">Author</th>  
                <th align="left">Genre</th>  
                <th align="left">Publish Date</th>  
                <th align="left">Price</th>  
              </tr>  
              <xsl:for-each select="book">  
                <tr>  
                  <td>  
                    <xsl:value-of select="title"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="author"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="genre"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="publish_date"/>  
                  </td>  
                  <xsl:choose>  
                    <xsl:when test="genre = 'Fantasy'">  
                      <td>  
                        <xsl:value-of select="user:discount(price)"/>  
                      </td>  
                    </xsl:when>  
                    <xsl:otherwise>  
                      <td>  
                        <xsl:value-of select="price"/>  
                      </td>  
                    </xsl:otherwise>  
                  </xsl:choose>  
                </tr>  
              </xsl:for-each>  
            </table>  
          </body>  
        </html>  
      </xsl:template>  
    </xsl:stylesheet>  
    ```  
  
- <span data-ttu-id="71164-107">Copie el archivo XML en su ordenador y llámelo `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="71164-107">Copy the XML file to your local computer and name it `books.xml`.</span></span>  
  
    ```xml  
    <?xml version="1.0"?>  
    <catalog>  
       <book id="bk101">  
          <author>Gambardella, Matthew</author>  
          <title>XML Developer's Guide</title>  
          <genre>Computer</genre>  
          <price>$44.95</price>  
          <publish_date>2000-10-01</publish_date>  
       </book>  
       <book id="bk102">  
          <author>Ralls, Kim</author>  
          <title>Midnight Rain</title>  
          <genre>Fantasy</genre>  
          <price>$5.95</price>  
          <publish_date>2000-12-16</publish_date>  
       </book>  
       <book id="bk103">  
          <author>Corets, Eva</author>  
          <title>Maeve Ascendant</title>  
          <genre>Fantasy</genre>  
          <price>$5.95</price>  
          <publish_date>2000-11-17</publish_date>  
       </book>  
       <book id="bk106">  
          <author>Randall, Cynthia</author>  
          <title>Lover Birds</title>  
          <genre>Romance</genre>  
          <price>$4.95</price>  
          <publish_date>2000-09-02</publish_date>  
       </book>  
       <book id="bk107">  
          <author>Thurman, Paula</author>  
          <title>Splish Splash</title>  
          <genre>Romance</genre>  
          <price>$4.95</price>  
          <publish_date>2000-11-02</publish_date>  
       </book>  
    </catalog>  
    ```  
  
### <a name="to-compile-the-style-sheet-with-the-script-enabled"></a><span data-ttu-id="71164-108">Para compilar la hoja de estilos con el script habilitado.</span><span class="sxs-lookup"><span data-stu-id="71164-108">To compile the style sheet with the script enabled.</span></span>  
  
1. <span data-ttu-id="71164-109">Si ejecuta la siguiente instrucción desde la línea de comandos, se crearán dos ensamblados, cuyos nombres son `Transform.dll` y `Transform_Script1.dll` (este es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="71164-109">Executing the following command from the command line creates two assemblies named `Transform.dll` and `Transform_Script1.dll` (This is the default behavior.</span></span> <span data-ttu-id="71164-110">A menos que se especifique lo contrario, el nombre de la clase y del ensamblado será, de forma predeterminada, el nombre de la hoja de estilos principal):</span><span class="sxs-lookup"><span data-stu-id="71164-110">Unless otherwise specified, the name of the class and the assembly defaults to the name of the main style sheet):</span></span>  
  
    ```console  
    xsltc /settings:script+ Transform.xsl  
    ```
  
    <span data-ttu-id="71164-111">La siguiente instrucción establece explícitamente el nombre de la clase en Transform:</span><span class="sxs-lookup"><span data-stu-id="71164-111">The following command explicitly sets the class name to Transform:</span></span>  
  
    ```console  
    xsltc /settings:script+ /class:Transform Transform.xsl  
    ```  
  
### <a name="to-include-the-compiled-assembly-as-a-reference-when-you-compile-your-code"></a><span data-ttu-id="71164-112">Para incluir el ensamblado compilado como referencia a la hora de compilar el código.</span><span class="sxs-lookup"><span data-stu-id="71164-112">To include the compiled assembly as a reference when you compile your code.</span></span>  
  
1. <span data-ttu-id="71164-113">Puede incluir un ensamblado en Visual Studio agregando una referencia en el Explorador de soluciones, o bien desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="71164-113">You can include an assembly in Visual Studio by adding a reference in the Solution Explorer, or from the command line.</span></span>  
  
2. <span data-ttu-id="71164-114">En C#, utilice lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="71164-114">For the command line with C#, use the following:</span></span>  
  
    ```console  
    csc myCode.cs /r:system.dll;system.xml.dll;Transform.dll  
    ```  
  
3. <span data-ttu-id="71164-115">En Visual Basic, utilice lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="71164-115">For the command line with Visual Basic, use the following</span></span>  
  
    ```console  
    vbc myCode.vb /r:system.dll;system.xml.dll;Transform.dll  
    ```  
  
### <a name="to-use-the-compiled-assembly-in-your-code"></a><span data-ttu-id="71164-116">Para utilizar el ensamblado compilado en su código.</span><span class="sxs-lookup"><span data-stu-id="71164-116">To use the compiled assembly in your code.</span></span>  
  
<span data-ttu-id="71164-117">El siguiente ejemplo muestra cómo ejecutar la transformación XSLT utilizando la hoja de estilos compilada.</span><span class="sxs-lookup"><span data-stu-id="71164-117">The following example shows how to execute the XSLT transformation by using the compiled style sheet.</span></span>  
  
[!code-csharp[XslTransform_XSLTC#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XslTransform_XSLTC/CS/XslTransform_XSLTC.cs#1)]
[!code-vb[XslTransform_XSLTC#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslTransform_XSLTC/VB/XslTransform_XSLTC.vb#1)]  
  
<span data-ttu-id="71164-118">Para vincular dinámicamente el ensamblado compilado, sustituya</span><span class="sxs-lookup"><span data-stu-id="71164-118">To dynamically link to the compiled assembly, replace</span></span>
  
```csharp  
xslt.Load(typeof(Transform));  
```  
  
<span data-ttu-id="71164-119">with</span><span class="sxs-lookup"><span data-stu-id="71164-119">with</span></span>  
  
```csharp
xslt.Load(System.Reflection.Assembly.Load("Transform").GetType("Transform"));  
```
  
<span data-ttu-id="71164-120">en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="71164-120">in the example above.</span></span> <span data-ttu-id="71164-121">Para obtener más información sobre el método Assembly. Load, vea <xref:System.Reflection.Assembly.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="71164-121">For more information on the Assembly.Load method, see <xref:System.Reflection.Assembly.Load%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71164-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="71164-122">See also</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform>
- [<span data-ttu-id="71164-123">Compilador XSLT (xsltc.exe)</span><span class="sxs-lookup"><span data-stu-id="71164-123">XSLT Compiler (xsltc.exe)</span></span>](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)
- [<span data-ttu-id="71164-124">Transformaciones XSLT</span><span class="sxs-lookup"><span data-stu-id="71164-124">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
- [<span data-ttu-id="71164-125">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="71164-125">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
