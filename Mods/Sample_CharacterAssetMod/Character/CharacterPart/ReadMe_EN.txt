Specifications for Character Part Modules:

1.Character parts are divided into hair, beard, hat, glasses, upper garment, lower garment, shoes, outerwear, and other accessories. Parts need to be annotated to define which sections they cover. It's important to note that a part can 	simultaneously be part of multiple sections, for example, a dress can serve as both upper and lower garments.
	Parts can be annotated for gender compatibility, specifying whether they are exclusive to male or female characters.
	Parts can be marked for visibility in the uniform editing interface.
	Specific model file names for parts need to be designated.
	Specific texture file names for parts need to be designated.
	Specific illustration file names for parts need to be designated.
	Model Specifications:

2.Models are used for displaying characters in-game scenes.
	The model file for character parts should include one and only one mesh with the same name as the part and a set of officially standard bones bound to it.
	Models should not have faces with more than four sides (triangles and quadrilaterals are preferred).
	Model textures should consist of two 128px * 64px PNG images: a color texture (baseMap_B) and a skin channel texture (skinMaskMap_M). Different part models within the same module can share textures.
	UV mapping of models should adapt to the model texture, and the texture should be used as the surface material.
	The number of faces in models should be kept within 2048 to avoid potential performance issues.

3.Illustration Files:
	Illustration files are used for displaying character headshots.
	Illustrations are displayed based on the categories marked by character parts. For example, if hair is defined, separate illustrations for front hair and back hair should be specified. If certain parts like lower garments are not intended to appear in the headshot, they can be omitted. Naming conventions should follow the format (part name_part type enum name.png), for example, (ExplosionHead_Hair.png).




Reference:
[System.Flags]
public enum PartMask
{
    Hair = 1 << 1,
    Upper = 1 << 2,
    Lower = 1 << 3,
    Shoe = 1 << 4,
    Eye = 1 << 5,
    Mouth = 1 << 6,
    Head = 1 << 7,
    Coat = 1 << 9,

    Hat = 1 << 10,
    Glass = 1 << 11,
    Mustache = 1 << 12,
    OtherDecorate = 1 << 13,
    Decorate = Glass | Hat | Mustache | OtherDecorate,
    All = Hair | Upper | Lower | Shoe | Eye | Mouth | Head | Decorate | Coat | Hat | Glass | Mustache | OtherDecorate,
}

