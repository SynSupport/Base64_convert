SUBMISSION AUTHOR:      Tod Phillips
                        mail to: tod.phillips@synergex.com
                        PSG
                        Synergex
                        2330 Gold Meadow Way
                        Gold River, CA 95670
                        Phone: 916-635-7300
                        http://www.synergex.com

SUBMISSION NAME:        Convert.dbl

PLATFORM:               Windows, VMS, Unix

SYNERGY VERSION:        Synergy v9.1.5 or higher

MODIFICATION HISTORY:   December 29th, 2008
                        September 20th, 2010 - Updated for compatibility with Synergy 9.5

DESCRIPTION:            Convert is a class that converts a base data type to another base data type.
                        Its current implementation has only one static method (ToBase64String) with
                        several overloads. It can be used in conjunction with the AsciiEncoding
                        class's "GetBytes" method (available as a separate download on the
                        CodeExchange) or instantiated with an alpha parameter instead.

ADDITIONAL NOTES:       In order to use this class, it must first be prototyped with the DBLPROTO
                        utility.  Ensure that your SYNIMPDIR and SYNEXPDIR environment variables
                        have been set, then run the protyper by typing:

                                dblproto Convert

                        from a command prompt in the directory where the Convert.dbl file has
                        been saved. (Alternately, import the file into a Workbench project, right-
                        click the project in the Projects tab and select "Generate Synergy
                        Protypes..."). The included file can then be compiled and added to any
                        library or ELB.  To use the provided class methods, simply type

                                import SynPSG.System

                        at the top of your source code. (See Example, below).

CLASS:                  Convert      (Public)

ENUMERATION(S):
        Public Enumeration Base64FormattingOptions
                 InsertLineBreaks
                 None

CONSTRUCTOR:
        None (Convert should include only static members, so it does not need
        instantiation to access its members).

PROPERTIES:
        None

METHOD(S):
        ToBase64String
                Overloaded. Converts the value of an array of 8-bit unsigned integers
                to its equivalent String representation encoded with base 64 digits.

                Usage & Overloads

                Convert.ToBase64String(a_ByteArray[#], Base64FormattingOptions)
                        a_ByteArray is a Dynamic System Array of 8-bit unsigned integers
                                to be converted to Base64
                        a_formatOption is a Base64FormattingOptions enumeration which causes
                                the method to either insert a line break every 76 characters (default),
                                or to not insert line breaks at all.

                Convert.ToBase64String(a_ByteArray[#])
                        a_ByteArray is a Dynamic System Array of 8-bit unsigned integers
                                to be converted to Base64.

                Convert.ToBase64String(a a_Alpha)
                        a_Alpha is an alphanumeric string that will be returned as a Base64 string


EXAMPLE(S):

        The following program demonstrates the use of the ToBase64String method.

;; Program to demonstrate the Convert.ToBase64String method.

import SynPSG.System

main
record
        b64String       ,string
        oldString       ,a256
endrecord

proc
        open(1,O,'TT:')
        oldString = "This is a test."
        writes(1,"Original String:")
                writes(1,%atrim(oldString))
                writes(1,"")
        b64String = Convert.ToBase64String(%atrim(oldString))
        writes(1,"Converted String:")
                writes(1,b64String)
end
