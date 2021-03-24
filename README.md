# Recuritment task

Please create data validator for given `Bank` class.
For invalid `Bank` instances exception should be thrown. For valid, do nothing.
Please commit code to this repository.

Validation should fail if:
* field `name` is longer than 7 letters
* field `name` is null or empty
* field `id` is null

Also please take into account the following instructions:
* write test cases in favourite framework
* follow own codestyle
* make code easy to understand and extend
* use at least one design pattern


`Bank` class:
```
import java.util.Objects;

public class Bank {
    private final Long id;
    private final String name;
    private final boolean active;

    public Bank(Long id, String name, boolean active) {
        this.id = id;
        this.name = name;
        this.active = active;
    }

    public Long getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    public boolean isActive() {
        return active;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Bank bank = (Bank) o;
        return active == bank.active && Objects.equals(id, bank.id) && Objects.equals(name, bank.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(id, name, active);
    }

    @Override
    public String toString() {
        return "Bank{" +
                "id=" + id +
                ", name='" + name + '\'' +
                ", active=" + active +
                '}';
    }
}
```

