# NegSampling
Negative Sampling for Mining First-order Logic Rules

## 1. Compilation

The Java source code should be compiled by `Maven`. The `pom.xml` file is provided with the code. Use `src/main/java/sinc2/Main.java` as the main class and package the project to a JAR archive `compress.jar`.
The compiled JAR package are also provided with the source code:
- `sinc.jar`: Use this package to run the original `SInC`
- `compress.jar`: Use this package to run compression with negative samples (except the adversarial sampling)
- `compress-adv.jar`: Use this package to run compression with adversarial negative sampling

## 2. Run

Use the `--help` or `-h` option to see all the options in this package:
```sh
$ java -jar sinc.jar --help
```

Run the following command without negative sampling:
```sh
$ java -jar sinc.jar -I path/to/KB KbName -O path/to/output OutputKbName
```

If negative samples are provided in the path `path/to/negative`, use the `-N` option to specify:
```sh
$ java -jar compress.jar -I path/to/KB KbName -O path/to/output OutputKbName -N path/to/negative NegKbName
```

The `-w` option turns on the weighting schema of negative samples in rule mining:
```sh
$ java -jar compress.jar -I path/to/KB KbName -O path/to/output OutputKbName -N path/to/negative NegKbName -w
```

## 3. Negative Sampling Methods

The methods of negative sampling is presented in `/src/main/java/sinc2/kb/NegSampler.java`. Change and run the `main()` method will produce negative samples as a negative KB. Supply the negative KB to `compress.jar` to compress KBs with negative samples.
