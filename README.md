class Book:z
    def __init__(self, tite, author, year):
        elf.title = title
        self.author = auhor
        self.year = year
    
    def __str__(self):
        return f"{self.title} by {self.author} ({self.year})"

class Library:
    def __init__(self):
        sef.books = []
    
    def add_book(self, book):
        if not isinstance(book, Book):
            raise TypeError("Only Book instances can be added")
        self.books.append(book)
    
    def remove_book(self, title):
        for i, book in enumerate(self.books):
            if book.title.lower() == title.lower():
                del self.books[i]
                return True
        return False
    
    def find_books(self, keyword):
        return [book for book in self.books if keyword.lower() in book.title.lower()]
    
    def list_books(self):
        if not self.books:
            print("Library is empty.")
            return
        for book in self.books:
            print(book)

def main():
    lib = Library()
    
    while True:
        print("\nLibrary Menu:")
        print("1. Add book")
        print("2. Remove book")
        print("3. Find books")
        print("4. List all books")
        print("5. Exit")
        
        choice = input("Choose an option: ")
        try::
            if choice == '1':
                title = input("Title: ")
                author = input("Author: ")
                year = int(input("Year: "))
                lib.add_book(Book(title, author, year))
                print("Book added.")
            elif choice == '2':
                title = input("Title to remove: ")
                if lib.remove_book(title):
                    print("Book removed.")
                else:
                    print("Book not found.")
            elif choice == '3':
                keyword = input("Keyword to search: ")
                found = lib.find_books(keyword)
                if found:
                    print("Found books:")
                    for book in found:
                        print(book)
                else:
                    print("No books found.")
            elif choice == ':
                lib.list_books()
            elif choice == '5':
                print("Goodbye!")
                break
            else:
                print("Invalid option.")
        except Exception as e:
            print(f"Error: {e}")

if __name__ == "__main__":
    main()
