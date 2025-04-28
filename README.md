def modify_and_write_file(input_filename, output_filename):
    """
    Reads a file, modifies each line, and writes the modified content to a new file.
    Handles potential file-related errors.
    """
    try:
        with open(input_filename, 'r') as infile:
            try:
                with open(output_filename, 'w') as outfile:
                    for line in infile:
                        # Example modification: Convert each line to uppercase
                        modified_line = line.upper()
                        outfile.write(modified_line)
                print(f"Successfully read '{input_filename}', modified it, and wrote to '{output_filename}'.")
            except IOError:
                print(f"Error: Could not write to the file '{output_filename}'.")
    except FileNotFoundError:
        print(f"Error: The input file '{input_filename}' was not found.")
    except IOError:
        print(f"Error: Could not read the file '{input_filename}'.")

if __name__ == "__main__":
    input_file = input("Enter the name of the file you want to read: ")
    output_file = "modified_" + input_file  # Create a default output filename
    modify_and_write_file(input_file, output_file)
