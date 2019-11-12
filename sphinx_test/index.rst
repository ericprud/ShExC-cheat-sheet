.. # define a hard line break for HTML
.. |br| raw:: html

   <br />

#######################
Compact ShEx by Example
#######################

.. toctree::
   :maxdepth: 2
   :caption: Contents:

================
Node Constraints
================

==================
Triple Constraints
==================

Cardinality
-----------

Example: In Shape ``school:Enrollee``, a Triple Constraint for triples:
* with property ``ex:hasGuardian`` 
* and with value of type IRI.

+---------------------------------------------------------------+--------------------------------------------+
| Matches exactly one such triple (the default).                                                             |
+---------------------------------------------------------------+--------------------------------------------+
| .. code-block:: json                                          | .. code-block::                            |
|    :emphasize-lines: 4                                        |    :emphasize-lines: 2                     |
|                                                               |                                            |
|    { "id": "http://school.example/#Enrollee",                 |    school:Enrollee {                       |
|      "type": "Shape",                                         |        ex:hasGuardian IRI                  |
|      "expression": {                                          |    }                                       |
|        "type": "TripleConstraint",                            |                                            |
|        "predicate": "http://ex.example/#hasGuardian",         |                                            |
|        "valueExpr": {                                         |                                            |
|          "type": "NodeConstraint",                            |                                            |
|          "nodeKind": "iri" } } }                              |                                            |
|                                                               |                                            |
+---------------------------------------------------------------+--------------------------------------------+
| ``+`` - Matches one or more such triples.                                                                  |
+---------------------------------------------------------------+--------------------------------------------+
| .. code-block:: json                                          | .. code-block::                            |
|    :emphasize-lines: 1                                        |    :emphasize-lines: 1                     |
|                                                               |                                            |
|        "type": "TripleConstraint", "min": 1, "max": -1,       |        ex:hasGuardian IRI +                |
|                                                               |                                            |
+---------------------------------------------------------------+--------------------------------------------+
| ``*`` - Matches zero or more such triples.                                                                 |
+---------------------------------------------------------------+--------------------------------------------+
| .. code-block:: json                                          | .. code-block::                            |
|    :emphasize-lines: 1                                        |    :emphasize-lines: 1                     |
|                                                               |                                            |
|        "type": "TripleConstraint", "min": 0, "max": -1,       |        ex:hasGuardian IRI *                |
|                                                               |                                            |
+---------------------------------------------------------------+--------------------------------------------+
| ``{m}`` - Matches exactly two such triples.                                                                |
+---------------------------------------------------------------+--------------------------------------------+
| .. code-block:: json                                          | .. code-block::                            |
|    :emphasize-lines: 1                                        |    :emphasize-lines: 1                     |
|                                                               |                                            |
|        "type": "TripleConstraint", "min": 2, "max": 2,        |        ex:hasGuardian IRI {2,}             |
|                                                               |                                            |
+---------------------------------------------------------------+--------------------------------------------+
| ``{m,n}`` - Matches at least one and no more than two such triples.                                        |
+---------------------------------------------------------------+--------------------------------------------+
| .. code-block:: json                                          | .. code-block::                            |
|    :emphasize-lines: 1                                        |    :emphasize-lines: 1                     |
|                                                               |                                            |
|        "type": "TripleConstraint", "min": 1, "max": 2,        |        ex:hasGuardian IRI {1,2}            |
|                                                               |                                            |
+---------------------------------------------------------------+--------------------------------------------+
