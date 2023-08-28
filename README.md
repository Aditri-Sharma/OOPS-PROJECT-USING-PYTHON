# OOPS-PROJECT-USING-PYTHON

# Design a ‘book’ class with title, author, publisher, price, and author’s royalty as instance variables. Provide getter and setter properties for all variables. Also, define a method royalty() to calculate royalty amount author can expect to receive the following royalties:10%  of the retail price on the first 500 copies; 12.5% for the next 1,000 copies sold, then 15% for all further copies sold. 

# Then design a new ‘ebook’ class inherited from the ‘book’ class. Add ebook format (EPUB, PDF,  MOBI, etc) as an additional instance variable in the inherited class.                                                                                                                                    Override royalty() method to deduct GST @12% on ebooks.

class book:
    def __init__(self,title,author,publisher,price,royalty):
        self.title=title
        self.author=author
        self.publisher=publisher
        self.price=price
        self.royalty=royalty
    def get_details(self):
        print("Title : ",self.title)
        print("Author : ",self.author)
        print("Publisher : ",self.publisher)
        print("Retail price : ",self.price)
        print("Royalty : ",self.royalty,"%","\n")
    def set_details(self,title,author,publisher,price,royalty):
        self.title=title
        self.author=author
        self.publisher=publisher
        self.price=price
        self.royalty=royalty
        print("Title : ",self.title)
        print("Author : ",self.author)
        print("Publisher : ",self.publisher)
        print("Price : ",self.price)
        print("Royalty : ",self.royalty,"%","\n")
    def royalty_find(self,copies_sold,royalty_new):
        print("For",copies_sold,"copies sold.............")
        p=(royalty_new/100)*self.price
        print("amount of royalty is : ",p,"\n")
class ebook(book):
    def __init__(self,title,author,publisher,price,royalty,ebook_format):
        super().__init__(title,author,publisher,price,royalty)
        self.ebook_format=ebook_format
    def royalty_find(self):
        self.price=self.price-((12/100)*self.price)
        print("PRICE OF EBOOK AFTER DEDUCTION : ",self.price)
        m=(self.royalty/100)*self.price
        print("Royalty amount after 12% deduction on GST : ",m)
p=book("A LADY ON A ROAD","RK SINHA","NDT TIMES",3000,5)
p.get_details()
print("setting details.............\n")
p.set_details("A WORLD OF WISDOM","SIDHARTH KESHAV","AA PUBLISHING",4000,10)
p.royalty_find(500,10)
p.royalty_find(1000,12.5)
p.royalty_find("futher all",15)
q=ebook("A LITTLE BUTTERFLY","SIDHARTH KESHAV","AMAZON",4400,10,"PDF")
q.royalty_find()
