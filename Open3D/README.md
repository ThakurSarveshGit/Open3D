<p align="center">
<img src="docs/_static/open3d_logo_horizontal.png" width="320" />
</p>

# Intel Programming Assessment

<h4>
	Table of Content

	1. Introduction
	2. Instructions to execute
	3. Assessment overview
	4. Results
</h4>


## 1. Introduction

	For the programming assessment, I have successfully completed the following tasks:

	1. Implemented C++ Function *open3d::geometry::TriangleMesh::IdenticallyColoredConnectedComponents* [x]
	2. Implemented Python binding for *open3d.geometry.TriangleMesh.identically_colored_connected_components* [x]
	3. Created *Solution.cpp* and executable*(Solution)* for testing the function. [x]
	4. Created *Solution.py* to test python binding for the function. [x]
	5. Wrote results to *Results.txt.* [x]
	6. Created and tested C++ unit tests. [x]
	7. Created and tested Python unit tests. [x]
	8. Provided documentation for code, build/run instructions and background about the algorithm used. [x]

## 2. Instructions to execute & test assessment
	1. Clone this repository and extract installation folder in a directory *(I have extracted on my Desktop)*.
	``
	2. Activate a virtual env(not necessary, but a better approach as given on forums)
	`cd ~/Desktop/Open3D`
	`conda activate my_env`
	3. Install dependencies
	`util/scripts/install-deps-ubuntu.sh`
	4. Create and navigate to build folder
	`mkdir build`
	`cd build`
	5. Configure
	`cmake -DPYTHON_EXECUTABLE=`which python` ..`
	6. Make the project (takes around 5-8 minutes)
	`make all -j$(nproc)`
	7. Create and Install the Open3D python package
	`make install-pip-package`
	8. Lookup executable locations on your system(Optional)
	`find . -executable -type f`
	9. Run the C++ executable *(Solution)*
	`cd ..`
	`./build/bin/examples/Solution`
	Result.txt will be inside the examples/TestData folder.
	10. Run Python Solution.py
	`python examples/Python/Basic/Solution.py`
	11. Run C++ UnitTests executable *(includes test for TriangleMesh::IdenticallyColoredConnectedComponents)*
	`./build/bin/unitTests`
	12. Run Python test
	`pytest src/UnitTest/Python/test_trianglemesh.py`

## 3. Assessment overview

	I enjoyed working on this programming assessment. It was interesting to work on a 3D dataset. I realized Open3D makes it easier to work on 3D datasets.

	![Given Dataset](docs/_static/Dataset.png)

	To navigate node graph, we can use any traversal algorithm. I chose Breadth-First-Search Algorithm for this assignment. I have kept the code resuable and implemented BFS as a separate private function. Optionally, depending upon the dataset nature, we can switch to various algorithms like DFS, BFS etc. supporting our case.

	Here are the following results I got while going through the assignments:
	
	1. [Result.txt](Results.txt)
	2. C++ Unit Test result *(All 233 tests run together, so including testcase for implemented function)*
	![C++ Unittest](cppTest.png)
	3. Pytest for testing python binding.
	![Pytest python binding](PythonTest.png)

## 4. Results
	BFS works correctly to find the interconnected nodes. We get multiple chains, for each color. If the dataset is disjoint, as in this case, we get multiple long chains for each color. For the sake of consistency with the output format described in the problem set, I have restricted the output to largest chains among each color among all the disjoint sets in the dataset.

	
	
	
	

## Supported OSes and compilers

* Ubuntu 18.04: GCC 5.x or newer [![Build Status](https://travis-ci.org/intel-isl/Open3D.svg?branch=master)](https://travis-ci.org/intel-isl/Open3D)[![Build Status](http://img.shields.io/travis/badges/badgerbadgerbadger.svg?style=flat-square)](https://travis-ci.org/badges/badgerbadgerbadger)