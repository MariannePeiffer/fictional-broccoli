le contenu de mon preprint est ici.



# The metadata file

## General information

The title is a field in the `metadata.json`:

~~~json
{
    "title": " test d'un fictional-Broccoli preprint"
}
~~~

## Authorship

Authors are listed as objects in the `authors` block. Each author is specified
as follows:

~~~json
{
      "familyname": "PEIFFER",
      "givennames": "Marianne",
      "email": "marianne.peifferb@inrae.fr",
      "orcid": "0000-0000-0000-0001",
      "affiliations": [
        "INRAE",
        "Affiliation 2"
      ],
      "status": ["corresponding", "equal"]
    }
~~~ 

The `email` field is recommended for all authors. The `status` field is only
useful for the corresponding author, and to denote equal contributions. These
informations are rendered on the initial page. If an `orcid` is given, it will
be linked on the HTML and PDF versions.

Note that there is *no need* to number the affiliations - a small python script
will take care of this automatically.

## Abstract




~~~json
"abstract": [
    "Point 1", le 1 er élément de mon résumé
    "Point 2" et le 2 ème élément de mon résumé
]
~~~




# References


~~~
[auth:fold]
[year]
[title:fold:nopunctordash:skipwords:lower:select=1,1:substring=1,3:capitalize]
[title:fold:nopunctordash:skipwords:lower:select=2,2:substring=1,3:capitalize]
~~~



# Figures, Tables, and other floats

Note that you can wrap the text of legends for both figures and tables. This
avoids the issue of having very long lines.

## Mathematics

The following equation

$$J'(p) = \frac{1}{\text{log}(S)}\times\left(-\sum p \times \text{log}(p)\right)$$ {#eq:eq1}

is produced using

~~~latex
$$J'(p) = \frac{1}{\text{log}(S)}\times ... $$ {#eq:eq1}
~~~

and can be referenced using `@eq:eq1`, which will result in @eq:eq1. Note that
because we use `pandoc-crossref`, the label "eq." will be generated
automatically.

## Tables

Table legends go on the line after the table itself. To generate a reference to
the table, use `{#tbl:id}` -- then, in the text, you can use `{@tbl:id}` to
refer to the table. For example, the table below is @tbl:id. You can remove the
*table* in front by using `!@tbl:id`, or force it to be capitalized with
`\*tbl:id`.

| Sepal.Length du BROCCOLI | Sepal.Widthdu BROCCOLI  | Petal.Length du BROCCOLI | Petal.Width du BROCCOLI | BROCCOLI |
|-------------------------:|------------------------:|-------------------------:|------------------------:|:--------|
|          5.1 |         3.5 |          1.4 |         0.2 | oui  |
|          5.0 |         3.6 |          1.4 |         0.2 | oui  |
|          5.4 |         3.9 |          1.7 |         0.4 | oui  |

Table: Tableau du TEST BROCCOLI, qui n'a pas de doi `id` -- we can refer to it using
`{@tbl:id}`. Note that even if the table legend is written below the table
itself, it will appear on top in the PDF document. {#tbl:id}

# Figures



~~~
![Image libre de droit de brocoli trouvée sur https://www.publicdomainpictures.net](figures/image.png){#fig:figure}
~~~

![Image libre de droit de brocoli trouvée sur https://www.publicdomainpictures.net](figures/image2.png){#fig:figure}

We can now use `@fig:figure` to refer to @fig:figure.

# Example text

Le brocoli est une variété de chou originaire de Sicile. Il fut sélectionné par les Romains à partir du chou sauvage
$$Co^\star=\frac{L-c_m}{T\times B-c_m} \,.$${#eq:cstar}

##  Brassica oleracea

un chou est un chou

##  Brassica oleracea var. italica

une variété italienne existe.



# References
