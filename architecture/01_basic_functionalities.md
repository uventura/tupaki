# Tupaki Basic Functionalities

## Main Goals to Achieve

 * Generate the virtual processor file
 * Run assembly files for a given processor

## Processor Generation

 | Processor Files | -> | Generator | -> | .tpk Artifact |

 * Processor File:
 	- .cpp file containing instructions implementation
	- .json file containing the processor architecture
 * Generator: Will generate the artifact containing a shared
 object, header files, notes, ...

 This solution will be created with:
```
    tupaki_binary(
	name = "my_processor",
	impl = "instructions.cpp",
	architecture = "archtecture.json",
	visibility = ["some_visibility"]
    )	
```

## Running Virtual Processor
 This step is responsible to test assembly files for a given
 processor, and can be done with the following rule:

```
    tupaky_project(
	name = "my_assembly_project",
	processor = ":my_processor",
	main = "main.asm",
	srcs = [
	    "main.asm",
	    "file1.asm",
	    "file2",
	    ...
	],
	data = [
	    "img/some_image.jpg",
	    "audio/some_txt.txt"
	],
	...
    )
```

