# Models and Relationships

Creating relationships between two models. Declare a function then return a relationship method from \$this model to another model.

E.g: User has many Projects = One to Many

```
public function projects() {
    return $this->hasMany(Project::class, 'creator_id', 'id');
}
```

First value is the Model it links too, second is the foreign key and third is the local key.

## Polymorphic Relationships
