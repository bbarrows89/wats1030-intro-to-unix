# Stretch Goals for the *nix Scavenger Hunt

The following goals are meant to provide a way for more experienced users to
extend their knowledge of the *nix command line.

* Use `curl` to look up the URL `http://www.imdb.com/title/tt0070948/`. The title of this film will lead you to the answer. *What is the answer?*

Using 'curl', I got the source for the page. I saw the title is Zardoz.

I then used grep to recursively search for instances of 'Zardoz' within the files in the project directory.

Bryans-MacBook-Air:wats1030-intro-to-unix bryan$ grep -r -n "Zardoz" .
./challenge_files/test2/explicabo_dolor.txt:2:Aperiam ipsam perferendis ut non est. Harum numquam officia veniam ea vel dolor. Unde vel vitae minima optio quas aliquamvel. Enim voluptatem autem culpa saepe. Alias ipsa Zardoz praesentium occaecati qui quaerat voluptas.

It appears as though the word Zardoz occurs once on the 2nd line of ./challenge_files/test2/explicabo_dolor.txt

I'm not entirely sure this is what I was meant to find, but it IS a match! 