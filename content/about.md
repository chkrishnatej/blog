---
title: "About"
date: 2021-07-12T07:26:50+05:30
draft: false
---

## Whis is this blog??
---
This is my digital space📖 where I share my thoughts💭, knowledge, and experiences about my dev journey. This would be a journal of my learnings trying to solve problems and sharing my learnings. I will be writing mostly about backend development and data engineering here. 

## Inspiration and ideology
---
> If you cannot explain something in simple terms, you do not understand it
>
> -- Richard Feynman

{{< hint info >}}
**Markdown content**\
Dolor sit, sumo unique argument um no. Gracie nominal id xiv. Romanesque acclimates investiture.
 Ornateness bland it ex enc, est yeti am bongo detract re.
{{< /hint >}}

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegexMatches {
    public static void main(String args[]) {

        // String to be scanned to find the pattern.
        String line = "This order was placed for QT3000! OK?";
        String pattern = "(.*)(\\d+)(.*)";

        // Create a Pattern object
        Pattern r = Pattern.compile(pattern);

        // Now create matcher object.
        Matcher m = r.matcher(line);
        if (m.find()) {
            System.out.println("Found value: " + m.group(0));
            System.out.println("Found value: " + m.group(1));
            System.out.println("Found value: " + m.group(2));
        } else {
            System.out.println("NO MATCH");
        }
    }
}
```
I believe in this and wanted to deliver it in writing medium. And it is a way of giving back to the community for me 🧑🏽‍💻 

My belief is that most sophisticated systems is built on robust basic building blocks. I try to scratch the metal trying to understand applications, solutions, and problems. Once building blocks are figured out, the systems can be built running the imaginations wild.

I like to figure out the building blocks and run my imaginations wild😃

## About me
---
I am Krishna Tej and I work as Software engineer. I develop backend API's with host of other techonologies. My primary programming language of choice is Python. I beleive in high quality over quantity. Learning to strike a balance to get the best of both worlds.


